<script lang="ts">
	export let href: string;
	export let title: string;
	export let description: string;
</script>

<a class="card" {href} target="_blank">
	<div class="img">
		<slot />
	</div>
	<div class="text">
		<div class="title">{title}</div>
		<div class="description">{description}</div>
	</div>
</a>

<style lang="scss">
	.card {
		--glow-size: 30rem;
		display: grid;
		height: fit-content;
		user-select: none;
		cursor: pointer;
		border-radius: var(--br);
		padding: 2rem;
		position: relative;
		z-index: 0;
		color: currentcolor;
		text-decoration: none;
		background-image: radial-gradient(
			var(--glow-size) circle at var(--x) var(--y),
			#fff4,
			transparent 50%
		);
		gap: 2rem;
		grid-template-columns: 5rem 1fr;
		&::before {
			content: "";
			inset: 0.1rem;
			position: absolute;
			border-radius: var(--br);
			background-color: var(--bg-00);
			z-index: -1;
		}
		&::after {
			content: "";
			transition: opacity 0.25s;
			opacity: 0;
			position: absolute;
			inset: 0;
			border-radius: var(--br);
			background-image: radial-gradient(
				30rem circle at var(--x) var(--y),
				#fff2,
				transparent 50%
			);
			z-index: -1;
		}
		&:hover {
			--glow-size: 70rem;
			&::after {
				opacity: 1;
			}
			&::before {
				inset: 0.2rem;
			}
		}
	}
	.img {
		display: grid;
		place-items: center;
	}
	.title {
		font-size: 1.8rem;
		grid-column: 2 / 3;
	}
	.description {
		margin-top: 0.5rem;
		color: var(--fg-02);
		font-size: 1.4rem;
		grid-column: 2 / 3;
	}
</style>
