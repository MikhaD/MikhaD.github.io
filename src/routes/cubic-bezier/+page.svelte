<script lang="ts">
	import { onMount } from "svelte";
	import CubicBezier from "./CubicBezier.svelte";
	import CubicBezierEditor from "./CubicBezierEditor.svelte";

	let x1 = 0;
	let y1 = 0.5;
	let x2 = 1;
	let y2 = 0.5;
	let loaded = false;

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
				x1 = parseFloat(components[0]);
				y1 = parseFloat(components[1]);
				x2 = parseFloat(components[2]);
				y2 = parseFloat(components[3]);
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
			<div class="item">
				<CubicBezier {x1} {y1} {x2} {y2} />
			</div>
		</div>
		<div class="track">
			<div class="item">
				<CubicBezier x1={0.25} y1={0.1} x2={0.25} y2={1} />
			</div>
		</div>
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
		grid-template-rows: auto 1fr 1fr;
		grid-template-areas:
			"ti ti"
			"ed di"
			"ed li";
	}
	.hl1 {
		color: var(--highlight-1);
	}
	.hl2 {
		color: var(--highlight-2);
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
	@media (max-width: 800px) {
		main {
			grid-template-columns: 1fr;
			grid-template-rows: repeat(4, auto);
			grid-template-areas:
				"ti"
				"ed"
				"di"
				"li";
		}
	}
</style>
