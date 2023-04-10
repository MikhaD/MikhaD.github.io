<script lang="ts">
	let x = 0;
	let y = 0;
	let container: HTMLElement;
	function onMouseMove(e: MouseEvent) {
		for (const child of container.childNodes) {
			if (child instanceof HTMLElement && child.classList.contains("card")) {
				const rect = child.getBoundingClientRect();
				child.style.setProperty("--x", `${e.clientX - rect.left}px`);
				child.style.setProperty("--y", `${e.clientY - rect.top}px`);
			}
		}
	}
</script>

<svelte:window on:mousemove={onMouseMove} />

<div class="container" bind:this={container}>
	<slot />
</div>

<style lang="scss">
	.container {
		min-height: 100%;
		max-width: var(--page-width);
		margin: 0 auto;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(40rem, 1fr));
		grid-gap: 1.5rem;
		--br: 0;
	}
</style>
