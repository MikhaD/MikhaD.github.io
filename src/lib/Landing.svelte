<script lang="ts">
	import BouncingArrow from "./BouncingArrow.svelte";
	import Github from "./icons/Github.svelte";
	import Linkedin from "./icons/Linkedin.svelte";
	import Youtube from "./icons/Youtube.svelte";
</script>

<section>
	<svg id="logo" viewBox="0 0 100 100">
		<mask id="cutout">
			<rect x="0" y="0" width="100%" height="100%" fill="#fff" />
			<path id="cutout-path" d="M0 -11l70 51c7 5 7 15 0 20l-70 51z" fill="#000" />
		</mask>
		<g mask="url(#cutout)">
			<path
				id="cog"
				class="v"
				fill-rule="evenodd"
				d="M53.706 0h-7.41l-2.085 5.537-5.878 1.17-4.044-4.32-6.845 2.835.192 5.914-4.983 3.33-5.39-2.443-5.24 5.24 2.44 5.4-3.33 4.983-5.913-.195L2.4 34.287l4.318 4.046-1.17 5.878-5.538 2.083v7.41l5.537 2.085 1.17 5.878L2.4 65.713l2.835 6.845 5.913-.195 3.33 4.983-2.44 5.4 5.24 5.24 5.39-2.443 4.983 3.33-.192 5.914 6.845 2.835 4.044-4.32 5.878 1.17L46.297 100h7.41l2.083-5.538 5.878-1.17 4.046 4.318 6.845-2.835-.195-5.913 4.983-3.33 5.4 2.44 5.24-5.24-2.443-5.39 3.33-4.983 5.914.192 2.835-6.845-4.32-4.044 1.17-5.878L100 53.703v-7.41l-5.538-2.083-1.17-5.878 4.32-4.044-2.835-6.845-5.914.192-3.33-4.983 2.443-5.39-5.24-5.24-5.4 2.44-4.983-3.33.195-5.913-6.845-2.835-4.046 4.318-5.878-1.17L53.706 0zM50 83.213c18.343 0 33.214-14.87 33.214-33.213S68.344 16.787 50 16.787 16.787 31.657 16.787 50 31.657 83.213 50 83.213z"
			/>
		</g>
		<path id="m" class="v" d="M7.5 24v52h7v-39l13 39l13 -39v39h7v-52h-10l-10 32l-10 -32z" />
	</svg>
	<div class="content">
		<div class="name-container">
			<div class="mikha name">Mikha</div>
			<div class="davids name">Davids</div>
		</div>
		<div class="links">
			<a class="link" href="https://github.com/MikhaD" target="_blank">
				<Github />
			</a>
			<a class="link" href="https://www.linkedin.com/in/mikha-davids/" target="_blank">
				<Linkedin />
			</a>
			<a class="link" href="https://www.youtube.com/@mikhadavids" target="_blank">
				<Youtube />
			</a>
		</div>
	</div>
	<a id="scroll-down" href="#projects">
		<BouncingArrow />
	</a>
</section>

<style lang="scss">
	#scroll-down {
		position: absolute;
		display: block;
		width: 4rem;
		height: 5rem;
		inset: auto 0 0 0;
		margin-inline: auto;
		color: var(--fg-01);
		opacity: 0;
		animation: fade-in 1s 3s ease-out forwards;
	}
	section {
		height: 100vh;
		height: 100dvh;
		position: relative;
		overflow-x: hidden;
	}
	.content {
		height: 100%;
		display: grid;
		gap: 2rem;
		place-content: center;
	}
	.name-container {
		--x-offset: 20.5rem;
		--x-offset: min(20.5rem, 20vw);
		font-size: clamp(6rem, 10vw, 10rem);
		font-weight: bold;
		text-transform: uppercase;
		text-align: center;

		div {
			width: fit-content;
		}
		--trans: 0%;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.name {
		line-height: 1.5ch;
		background: var(--bg-gradient);
		-webkit-background-clip: text;
		background-clip: text;
		-webkit-text-fill-color: transparent;
		color: transparent;
		background-size: 140% 180%;
		opacity: 0;
		animation: fade-in 1s 2s ease-out forwards;
		user-select: none;
	}
	.mikha {
		margin-right: var(--x-offset);
		transform: translateX(-90%);
	}
	.davids {
		display: flex;
		align-items: start;
		background-position: 100% 100%;
		transform: translateX(90%);
		margin-left: var(--x-offset);
	}
	.links {
		display: flex;
		height: 4rem;
		justify-content: center;
		gap: 10vmin;
	}
	.link {
		color: var(--fg-01);
		opacity: 0;
		height: 100%;
		transform: translateY(5rem);
		animation: fade-in 0.5s ease-out forwards;
		img {
			height: 100%;
		}
	}
	@for $i from 1 through 3 {
		.link:nth-child(#{$i}) {
			animation-delay: #{2.5 + 0.1 * $i}s;
		}
	}

	#logo {
		position: absolute;
		z-index: -1;
		height: 100%;
		width: 100%;
		padding: 8vmax;
		animation: fade-out 0.6s 2s ease-out forwards;
		fill: var(--fg-00);
	}
	#cog {
		animation: cog 2s ease-out;
		transform-origin: center;
		transform-box: fill-box;
	}

	#cutout-path {
		transform: translateX(-100%);
		animation: cutout 1s 0.6s ease-out;
		animation-fill-mode: forwards;
	}

	#m {
		transform: scale(0);
		animation: m 0.6s 1s ease-out;
		animation-fill-mode: forwards;
		transform-origin: center;
		transform-box: fill-box;
	}

	@keyframes cog {
		from {
			transform: rotate(0deg);
		}

		to {
			transform: rotate(180deg);
		}
	}

	@keyframes cutout {
		to {
			transform: translateX(0%);
		}
	}

	@keyframes m {
		to {
			transform: scale(1);
		}
	}

	@keyframes fade-out {
		from {
			padding: 8vmax;
			opacity: 1;
			fill: var(--fg-00);
		}

		to {
			padding: 0;
			opacity: 0;
			fill: black;
		}
	}
	@keyframes fade-in {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
			transform: translate(0%, 0%);
		}
	}
	@keyframes bouncing-arrow {
		0% {
			transform: translateY(0);
		}
		70% {
			transform: translateY(50%);
		}
		100% {
			transform: translateY(0%);
		}
	}
</style>
