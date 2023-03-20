<script lang="ts">
	import Swatch from "./Swatch.svelte";
</script>

<svelte:head>
	<title>Palette</title>
</svelte:head>

<Swatch hue={0} saturation={100} colors={10} />
<Swatch hue={0} saturation={0} colors={10} />
<Swatch hue={180} saturation={100} colors={10} />
<Swatch hue={180} saturation={10} colors={10} increment={2} />

<style lang="scss">
	:global(body) {
		background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 2 2'%3E%3Cpath d='M0 0H2V2H0z' fill='%238F8F8F'/%3E%3Cpath d='M0 0H1V2H2V1H0z' fill='%23969696'/%3E%3C/svg%3E");
		background-size: 3rem;
	}
</style>
