<script lang="ts">
	import Input from "$lib/Input.svelte";
	import Password from "$lib/Password.svelte";

	let value = "";
</script>

<svelte:head>
	<title>Login</title>
</svelte:head>

<h1>Login</h1>
<Password label="Password" bind:value />
