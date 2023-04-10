<script context="module" lang="ts">
	let ids = 0;
	let base_id = Date.now();
	function UID() {
		return "input-" + (++ids + base_id).toString(32);
	}
</script>

<script lang="ts">
	export let label: string;
	export let value: string = "";
	export let hidden: boolean = true;

	const id = UID();
	let input: HTMLInputElement;

	function onInput(e: Event & { currentTarget: EventTarget & HTMLInputElement }) {
		value = e.currentTarget.value;
	}
	$: input && (input.value = value);
</script>

<span class:content={value.length > 0}>
	<input
		bind:this={input}
		type={hidden ? "password" : "text"}
		autocomplete="current-password"
		{id}
		on:input={onInput}
	/>
	<label for={id}>{label}</label>
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<svg viewBox="0 0 16 16" width="2.5rem" on:click={() => (hidden = !hidden)}>
		<mask id="show-line">
			<path d="M0 0H16V16H0z" fill="#fff" />
			<path d="M3.41 2l9 9" stroke="#000" style:visibility={!hidden ? "hidden" : "visible"} />
		</mask>
		<g mask="url(#show-line)">
			<path d="M2.5 8.5a5.8 5.8 0 01 11 0" fill="none" />
			<circle cx="8" cy="9.5" r="2" />
			<path d="M2.5 2.5l11 11" style:visibility={!hidden ? "hidden" : "visible"} />
		</g>
	</svg>
</span>

<style lang="scss">
	span {
		--trans: 0.1s ease-in-out;
		display: inline-grid;
		position: relative;
		color: var(--fg-00);
		padding-top: 0.5em;
		border-bottom: solid var(--fg-01) 1px;
		grid-template-columns: 1fr 2.5rem;
	}
	input {
		border: none;
		padding-block: 0.5em;
		background-color: transparent;
		transition: border var(--trans);
		color: inherit;
		font: inherit;
		outline: none;
		width: 100%;
		grid-row: 1 / 2;
		grid-column: 1 / 2;
	}
	svg {
		place-self: center;
		cursor: pointer;
		stroke: var(--fg-01);
		fill: var(--fg-01);
		stroke-linecap: round;
	}
	label {
		transition: var(--trans);
		position: absolute;
		color: var(--fg-01);
		top: 1em;
		left: 0;
		cursor: text;
	}
	span.content,
	span:focus-within {
		label {
			color: inherit;
			font-size: 0.8em;
			transform: translateY(-100%);
		}
		input {
			border-color: currentcolor;
		}
		svg {
			stroke: currentcolor;
			fill: currentcolor;
		}
	}
</style>
