<script>
	import { onMount } from "svelte";
	import JS from "./script.js";
	import "./style.css";

	onMount(JS);
</script>

<svelte:head>
	<link rel="icon" />
	<title>Imitation Garden</title>
</svelte:head>
<main />
<div class="notice">
	<div>
		<h2>Congratulations!</h2>
		<p>You have successfully wasted <span class="wasted-time" />of your time!</p>
	</div>
	<div class="close">×</div>
</div>
