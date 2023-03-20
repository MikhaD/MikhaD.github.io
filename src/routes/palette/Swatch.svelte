<script lang="ts">
	export let hue = 0;
	export let saturation = 100;
	export let colors = 5;
	export let increment = 5;
</script>

<div>
	{#each new Array(colors) as _, i}
		<span class="color" style="background-color: hsl({hue} {saturation}% {i * increment}%)" />
	{/each}
</div>

<style lang="scss">
	.color {
		display: inline-block;
		width: 5rem;
		height: 5rem;
	}
</style>
