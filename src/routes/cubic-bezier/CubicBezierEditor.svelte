<script lang="ts">
	import { createEventDispatcher } from "svelte";
	import { svg_x, svg_y } from "./utils";

	export let x1: number;
	export let y1: number;
	export let x2: number;
	export let y2: number;

	const enum Selected {
		none,
		left,
		right,
	}

	const dispatch = createEventDispatcher();

	let editor: SVGSVGElement;
	let dragging: boolean;
	let selected: Selected = Selected.none;
	let within = false;
	let time = 0;
	let progression = 0;

	function onClick(e: MouseEvent) {
		if ((e.target as HTMLElement)?.classList.contains("ctrl")) return;
		setCtrlPoint(selected, e.clientX, e.clientY, editor.getBoundingClientRect());
		dispatch("set", { x1, y1, x2, y2 });
	}

	function onMove(e: MouseEvent) {
		if (within) {
			time = (100 * e.offsetX) / editor.clientWidth;
			progression = (100 * e.offsetY) / editor.clientHeight;
		}
		if (!dragging) return;
		setCtrlPoint(selected, e.clientX, e.clientY, editor.getBoundingClientRect());
	}

	function clamp(min: number, val: number, max: number) {
		return Math.max(Math.min(val, max), min);
	}

	function setCtrlPoint(point: Selected, x: number, y: number, bcr: DOMRect) {
		if (point === Selected.left) {
			x1 = clamp(0, (x - bcr.left) / editor.clientWidth, 1);
			y1 = 1 - (y - bcr.top) / editor.clientHeight;
		} else if (point === Selected.right) {
			x2 = clamp(0, (x - bcr.left) / editor.clientWidth, 1);
			y2 = 1 - (y - bcr.top) / editor.clientHeight;
		}
	}

	function deSelect(e: MouseEvent) {
		if (!editor.contains(e.target as Node)) {
			selected = Selected.none;
		}
	}

	function onKeypress(e: KeyboardEvent) {
		switch (e.key) {
			case "Escape":
				selected = Selected.none;
				break;
			case "ArrowLeft":
				e.preventDefault();
				if (selected === Selected.left) {
					x1 = clamp(0, x1 - 0.01, 1);
				} else if (selected === Selected.right) {
					x2 = clamp(0, x2 - 0.01, 1);
				}
				break;
			case "ArrowRight":
				e.preventDefault();
				if (selected === Selected.left) {
					x1 = clamp(0, x1 + 0.01, 1);
				} else if (selected === Selected.right) {
					x2 = clamp(0, x2 + 0.01, 1);
				}
				break;
			case "ArrowUp":
				e.preventDefault();
				if (selected === Selected.left) {
					y1 += 0.01;
				} else if (selected === Selected.right) {
					y2 += 0.01;
				}
				break;
			case "ArrowDown":
				e.preventDefault();
				if (selected === Selected.left) {
					y1 -= 0.01;
				} else if (selected === Selected.right) {
					y2 -= 0.01;
				}
				break;
		}
	}

	function stopDragging() {
		if (dragging) {
			dispatch("set", { x1, y1, x2, y2 });
		}
		dragging = false;
	}
</script>

<svelte:window on:mousemove={onMove} on:mouseup={stopDragging} on:mousedown={deSelect} />

<div
	tabindex="-1"
	on:keydown={onKeypress}
	on:mouseenter={() => (within = true)}
	on:mouseleave={() => (within = false)}
>
	<span class="x-axis">
		Time
		{#if within}
			({Math.round(time)}%)
		{/if}
	</span>
	<span class="y-axis">
		Progression
		{#if within}
			({100 - Math.round(progression)}%)
		{/if}
	</span>
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<svg
		viewBox="0 0 100 100"
		width="100%"
		fill="none"
		class="overflow-visible"
		on:click={onClick}
		on:mousedown={() => (dragging = true)}
		bind:this={editor}
	>
		<!-- Background grid -->
		<path
			d="M0 10h100M0 20h100M0 30h100M0 40h100M0 50h100M0 60h100M0 70h100M0 80h100M0 90h100M10 0v100M20 0v100M30 0v100M40 0v100M50 0v100M60 0v100M70 0v100M80 0v100M90 0v100"
			stroke-width=".1"
			class="transparent-bg-element"
		/>
		<!-- Axes -->
		<path d="M0 0v100h100" stroke-width="1" />
		<!-- Background Diagonal -->
		<path
			d="M0 100L100 0"
			stroke-width="2"
			class="transparent-bg-element"
			class:clickable={selected === Selected.none}
			on:click|self={() => {
				if (selected !== Selected.none) return;
				x1 = 0;
				y1 = 0;
				x2 = 1;
				y2 = 1;
			}}
		/>
		<!-- The curve -->
		<path d="M0 100 C{svg_x(x1)} {svg_y(y1)} {svg_x(x2)} {svg_y(y2)} 100 0" stroke-width="2" />
		<!-- Control point lines -->
		<path
			d="M0 100 L{svg_x(x1)} {svg_y(y1)}"
			stroke-width=".5"
			class="ctrl ctrl-line"
			class:active={selected === Selected.left}
			on:mousedown={() => (selected = Selected.left)}
		/>
		<path
			d="M100 0 L{svg_x(x2)} {svg_y(y2)}"
			stroke-width=".5"
			class="ctrl ctrl-line"
			class:active={selected === Selected.right}
			on:mousedown={() => (selected = Selected.right)}
		/>
		<!-- Diagonal end cap circles -->
		<circle cx="0" cy="100" r="1.5" class="end" />
		<circle cx="100" cy="0" r="1.5" class="end" />
		<!-- Control point ends -->
		<circle
			cx={svg_x(x1)}
			cy={svg_y(y1)}
			r="2.5"
			class="ctrl ctrl-end left"
			on:mousedown={() => (selected = Selected.left)}
			class:active={selected === Selected.left}
		/>
		<circle
			cx={svg_x(x2)}
			cy={svg_y(y2)}
			r="2.5"
			class="ctrl ctrl-end right"
			on:mousedown={() => (selected = Selected.right)}
			class:active={selected === Selected.right}
		/>
	</svg>
</div>

<style lang="scss">
	div {
		--size: 30rem;
		border-radius: 0.5rem;
		width: var(--size);
		height: var(--size);
		position: relative;
		margin-block: calc(var(--size) / 2);
		user-select: none;
		margin-left: 2rem;
	}
	svg {
		overflow: visible;
		position: absolute;
		stroke: var(--fg-00);
	}
	span {
		position: absolute;
		text-transform: uppercase;
		font-size: 1.2rem;
	}
	.x-axis {
		opacity: 0.5;
		top: 101%;
		left: 0;
	}
	.y-axis {
		opacity: 0.5;
		transform: rotate(-90deg);
		transform-origin: 0 0;
		left: -7%;
		bottom: -5%;
	}
	.transparent-bg-element {
		opacity: 0.3;
	}
	.end {
		fill: var(--fg-00);
		stroke: none;
	}
	.ctrl-end {
		fill: var(--bg-00);
		stroke-width: 0.2;
		&.left {
			fill: var(--highlight-1);
		}
		&.right {
			fill: var(--highlight-2);
		}
	}
	.ctrl-end,
	.ctrl-line {
		cursor: pointer;
		&:hover {
			stroke: teal;
			stroke-width: 0.5;
		}
	}
	.ctrl-end.active {
		stroke: teal;
		stroke-width: 1;
	}
	.ctrl-line.active {
		stroke: teal;
	}
	.clickable {
		cursor: pointer;
	}
</style>
