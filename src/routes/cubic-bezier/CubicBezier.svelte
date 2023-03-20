<script lang="ts">
	import { svg_x, svg_y } from "./utils";

	export let x1: number;
	export let y1: number;
	export let x2: number;
	export let y2: number;
</script>

<span>
	<svg viewBox="0 0 100 100" fill="none" width="100%">
		<circle cx={svg_x(x1)} cy={svg_y(y1)} r="1.7" />
		<circle cx={svg_x(x2)} cy={svg_y(y2)} r="1.7" />
		<path d="M0 100 L{svg_x(x1)} {svg_y(y1)}" stroke="white" stroke-width="1" />
		<path d="M100 0 L{svg_x(x2)} {svg_y(y2)}" stroke="white" stroke-width="1" />
		<path
			d="M0 100 C{svg_x(x1)} {svg_y(y1)} {svg_x(x2)} {svg_y(y2)} 100 0"
			stroke="white"
			stroke-width="3"
		/>
	</svg>
</span>

<style lang="scss">
	span {
		display: inline-flex;
		justify-content: center;
		align-items: center;
		background-color: var(--highlight-1);
		border-radius: 0.5rem;
		padding: 10%;
		overflow: hidden;
	}
	svg {
		overflow: visible;
	}
	circle {
		fill: #fff;
	}
</style>
