<script lang="ts">
	import { onMount } from "svelte";
	import CubicBezier from "./CubicBezier.svelte";
	import CubicBezierEditor from "./CubicBezierEditor.svelte";

	let x1 = 0;
	let y1 = 0.5;
	let x2 = 1;
	let y2 = 0.5;
	let loaded = false;
	let animation_key = false;

	function format(n: number) {
		let result = n.toFixed(2);
		result = result.replace(/^0/, "");
		result = result.replace(/\.?0+$/, "");
		return result || "0";
	}

	onMount(() => {
		loaded = true;
		if (document.location.hash) {
			const components = document.location.hash.slice(1).split(",");
			if (components.length === 4) {
				[x1, y1, x2, y2] = components.map(parseFloat);
			}
		}
	});

	function bezierSet() {
		document.location.hash = `${format(x1)},${format(y1)},${format(x2)},${format(y2)}`;
	}
</script>

<svelte:head>
	<title>Cubic Bezier Generator</title>
</svelte:head>

<main>
	<h1 class="title">
		cubic-bezier(<span class="hl1">{format(x1)}</span>,
		<span class="hl1">{format(y1)}</span>,
		<span class="hl2">{format(x2)}</span>,
		<span class="hl2">{format(y2)}</span>)
	</h1>
	<div class="editor">
		<CubicBezierEditor bind:x1 bind:y1 bind:x2 bind:y2 on:set={bezierSet} />
	</div>
	<section class="display">
		<div class="track">
			{#key animation_key}
				<div
					class="item custom-bezier"
					style="animation-timing-function: cubic-bezier({x1}, {y1}, {x2}, {y2})"
				>
					<CubicBezier {x1} {y1} {x2} {y2} />
				</div>
			{/key}
		</div>
		<div class="track">
			{#key animation_key}
				<div class="item">
					<CubicBezier x1={0.25} y1={0.1} x2={0.25} y2={1} />
				</div>
			{/key}
		</div>
	</section>
	<section class="controls">
		<button on:click={() => (animation_key = !animation_key)}>Play Animation</button>
	</section>
	<section class="library">
		<div class="timing-function">
			<CubicBezier x1={0.25} y1={0.1} x2={0.25} y2={1} />
			<div>ease</div>
		</div>
		<div class="timing-function">
			<CubicBezier x1={0.42} y1={0} x2={1} y2={1} />
			<div>ease-in</div>
		</div>
		<div class="timing-function">
			<CubicBezier x1={0} y1={0} x2={0.58} y2={1} />
			<div>ease-out</div>
		</div>
		<div class="timing-function">
			<CubicBezier x1={0.42} y1={0} x2={0.58} y2={1} />
			<div>ease-in-out</div>
		</div>
		<div class="timing-function">
			<CubicBezier x1={0} y1={0} x2={1} y2={1} />
			<div>linear</div>
		</div>
	</section>
</main>

<style lang="scss">
	main {
		--highlight-1: hsl(180, 75%, 35%);
		--highlight-2: hsl(280 75% 35%);
		max-width: 140rem;
		padding-inline: 2rem;
		min-height: 100%;
		margin: 0 auto;
		display: grid;
		gap: 2rem;
		grid-template-columns: auto 1fr;
		grid-template-rows: auto 2fr auto 2fr;
		grid-template-areas:
			"ed ti"
			"ed di"
			"ed co"
			"ed li";
	}
	.hl1 {
		color: var(--highlight-1);
	}
	.hl2 {
		color: var(--highlight-2);
	}
	button {
		color: currentcolor;
		background-color: var(--highlight-1);
		border: none;
		padding: 1rem;
		font-size: 1.8rem;
		border-radius: 0.5rem;
		cursor: pointer;
	}
	.timing-function {
		width: 9rem;
		text-align: center;
		display: inline-block;
	}
	.title {
		font-family: var(--font-mono);
		grid-area: ti;
		text-align: center;
	}
	.editor {
		grid-area: ed;
		margin: auto;
	}
	.display {
		grid-area: di;
		width: 100%;
		padding-inline: 5vw;
		display: grid;
		align-content: center;
	}
	.controls {
		grid-area: co;
		display: grid;
	}
	.library {
		display: flex;
		flex-wrap: wrap;
		align-content: start;
		justify-content: center;
		gap: 1rem;
		grid-area: li;
	}

	.track {
		position: relative;
		margin-bottom: 1rem;
	}
	.item {
		width: 5rem;
		height: 5rem;
		border-radius: 50%;
		background-color: var(--highlight-1);
		overflow: hidden;
		padding: 0.5rem;
		transform: translateX(-50%);
		animation: move 1s forwards;
	}
	.track::before {
		content: "";
		z-index: -1;
		position: absolute;
		width: 100%;
		top: 50%;
		background-color: var(--fg-00);
		height: 1px;
	}
	@keyframes move {
		0% {
			margin-left: 0;
		}
		100% {
			margin-left: 100%;
		}
	}
	@media (max-width: 800px) {
		main {
			grid-template-columns: 1fr;
			grid-template-rows: repeat(4, auto);
			grid-template-areas:
				"ti"
				"ed"
				"di"
				"co"
				"li";
		}
	}
</style>
