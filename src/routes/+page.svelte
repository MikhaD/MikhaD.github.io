<script lang="ts">
	import { goto } from "$app/navigation";
	import MAC from "$lib/MouseAuraCards.svelte";

	let typingTimeout: number;
	let str = "";

	function onKeypress(event: KeyboardEvent) {
		clearTimeout(typingTimeout);
		typingTimeout = setTimeout(() => {
			str = "";
		}, 500);
		str += event.key;
		if (str === "MikhaD") {
			goto("/login");
		}
	}
</script>

<svelte:window on:keypress={onKeypress} />

<svelte:head>
	<title>Mikha's Portfolio</title>
</svelte:head>

<h1>Mikha's Portfolio Website Coming Soon</h1>
<svg viewBox="0 0 100 100" fill="currentcolor" class="logo">
	<mask id="cutout">
		<rect x="0" y="0" width="100%" height="100%" fill="#fff" />
		<path fill="#000" id="cutout-path" d="M0 -11l70 51c7 5 7 15 0 20l-70 51z" />
	</mask>
	<g mask="url(#cutout)">
		<path
			id="cog"
			fill-rule="evenodd"
			d="M53.706 0h-7.41l-2.085 5.537-5.878 1.17-4.044-4.32-6.845 2.835.192 5.914-4.983 3.33-5.39-2.443-5.24 5.24 2.44 5.4-3.33 4.983-5.913-.195L2.4 34.287l4.318 4.046-1.17 5.878-5.538 2.083v7.41l5.537 2.085 1.17 5.878L2.4 65.713l2.835 6.845 5.913-.195 3.33 4.983-2.44 5.4 5.24 5.24 5.39-2.443 4.983 3.33-.192 5.914 6.845 2.835 4.044-4.32 5.878 1.17L46.297 100h7.41l2.083-5.538 5.878-1.17 4.046 4.318 6.845-2.835-.195-5.913 4.983-3.33 5.4 2.44 5.24-5.24-2.443-5.39 3.33-4.983 5.914.192 2.835-6.845-4.32-4.044 1.17-5.878L100 53.703v-7.41l-5.538-2.083-1.17-5.878 4.32-4.044-2.835-6.845-5.914.192-3.33-4.983 2.443-5.39-5.24-5.24-5.4 2.44-4.983-3.33.195-5.913-6.845-2.835-4.046 4.318-5.878-1.17L53.706 0zM50 83.213c18.343 0 33.214-14.87 33.214-33.213S68.344 16.787 50 16.787 16.787 31.657 16.787 50 31.657 83.213 50 83.213z"
		/>
	</g>
	<path id="m" d="M7.5 24v52h7v-39l13 39l13 -39v39h7v-52h-10l-10 32l-10 -32z" />
</svg>
<h2>Projects</h2>
<div>Projects who's names end with a * are incomplete and still being actively worked on.</div>
<MAC.Container>
	<MAC.Card
		href="https://mikhad.github.io/minesweeper/"
		title="Minesweeper*"
		description="I played minesweeper on my phone until the app started showing ads, so I made my own."
	>
		<svg viewBox="0 0 100 100" fill="currentcolor" stroke-linecap="round">
			<mask id="bomb-mask" fill="#000">
				<path d="M0 0H100V100H0z" fill="#fff" />
				<path d="M26 46a5 5 0 00 10 0a10 10 0 01 10-10a5 5 0 10 0-10a20 20 0 00-20 20z" />
			</mask>
			<g mask="url(#bomb-mask)">
				<circle cx="50" cy="50" r="35" />
				<path
					d="M50 5V95M5 50H95M18 18L82 82M82 18L18 82"
					stroke="currentcolor"
					stroke-width="12"
				/>
			</g>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/wordle"
		title="Wordle+"
		description="My recreation of the popular word game Wordle with infinite & hourly modes, word definitions & more."
	>
		<svg viewBox="0 0 100 100" fill="currentcolor">
			<path
				d="M13.024 22H0L15.096 78H27.824L37 40.2737L46.176 78H58.904L74 22H60.976L52.392 59.7263L42.624 22H31.376L21.608 59.7263L13.024 22Z"
			/>
			<path d="M72 53.48H81.52V63H90.48V53.48H100V44.52H90.48V35H81.52V44.52H72V53.48Z" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://peacediscipline.com/"
		title="Peace Discipline Website"
		description="The website for my mother's business, Peace Discipline."
	>
		<svg viewBox="0 0 732 571" fill="currentcolor">
			<circle r="116" cx="548" cy="454" />
			<circle r="46" cx="684" cy="349" />
			<circle r="32" cx="676" cy="260" />
			<circle r="64" cx="577" cy="223" />
			<circle r="32" cx="492" cy="288" />
			<circle r="38" cx="483" cy="155" />
			<circle r="79" cx="372" cy="219" />
			<circle r="38" cx="325" cy="337" />
			<circle r="46" cx="378" cy="417" />
			<circle r="14" cx="338" cy="503" />
			<circle r="34" cx="262" cy="491" />
			<circle r="14" cx="213" cy="439" />
			<circle r="23" cx="164" cy="472" />
			<circle r="34" cx="109" cy="412" />
			<circle r="14" cx="170" cy="386" />
			<circle r="23" cx="197" cy="334" />
			<circle r="14" cx="150" cy="313" />
			<circle r="14" cx="97" cy="317" />
			<circle r="34" cx="34" cy="303" />
			<circle r="14" cx="62" cy="252" />
			<circle r="14" cx="203" cy="259" />
			<circle r="14" cx="139" cy="248" />
			<circle r="14" cx="185" cy="212" />
			<circle r="34" cx="93" cy="156" />
			<circle r="14" cx="155" cy="162" />
			<circle r="14" cx="222" cy="148" />
			<circle r="14" cx="182" cy="103" />
			<circle r="14" cx="248" cy="98" />
			<circle r="34" cx="304" cy="66" />
			<circle r="14" cx="359" cy="33" />
			<circle r="14" cx="405" cy="53" />
			<circle r="34" cx="463" cy="34" />
			<circle r="14" cx="515" cy="68" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="./cubic-bezier"
		title="Cubic Bezier Creator*"
		description="A tool to create cubic bezier curves for use in CSS animations."
	>
		<svg viewBox="0 0 100 100" fill="none" stroke="currentcolor">
			<circle cx="80" cy="90" r="5" fill="currentcolor" />
			<circle cx="20" cy="10" r="5" fill="currentcolor" />
			<path d="M0 100 L80 90" stroke-width="2" />
			<path d="M100 0 L20 10" stroke-width="2" />
			<path d="M0 100 C80 90 20 10 100 0" stroke-width="5" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/nfr-bot"
		title="Discord Bot"
		description="A tool for display info from the Wynncraft API, with additional fun and QoL commands."
	>
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 6 6" fill="currentcolor">
			<path d="M3 0H5V1H6V2H4V3H3V5H4V6H2V4H1V3H0V2H2V1H3z" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/flexbox-sandbox/"
		title="Flexbox Sandbox"
		description="A tool to help you learn flexbox and experiment with different flex properties."
	>
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" fill="currentcolor">
			<path d="M0 38h24v24H0zM32 32h36v36h-36zM100 38v24h-24v-24z" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/what-the-weather"
		title="What the Weather"
		description="A simple vanilla JS app to find the weather in different countries or cities using openweathermap."
	>
		<svg viewBox="0 0 100 100" fill="currentcolor" stroke-linecap="round">
			<path d="m14 65a1 1 0 01 10-35a26 26 0 01 50-7a7 7 0 01 10 10a1 1 0 01 0 32z" />
			<path
				d="M20 76l2 4M40 71l2 4M55 86l2 4M65 74l2 4M83 78l2 4"
				stroke="currentcolor"
				stroke-width="5"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="./morse-mangler"
		title="Morse Mangler"
		description="A tool I created in high school for converting to & from morse code for my friend and I."
	>
		<svg viewBox="0 0 100 100" fill="currentcolor" stroke-linecap="round">
			<mask id="morse-mask">
				<path d="M0 0H100V100H0z" fill="#fff" />
				<circle cx="57" cy="60" r="7.5" fill="#000" />
				<circle cx="77" cy="60" r="7.5" fill="#000" />
				<rect x="15" y="35" width="30" height="15" fill="#000" rx="5" />
			</mask>
			<circle mask="url(#morse-mask)" cx="50" cy="50" r="50" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/svelte-component-library/"
		title="Svelte Component Library"
		description="A growing collection of all my reusable Svelte components, SVGs & animations."
	>
		<svg viewBox="0 0 100 100" fill="none" stroke="currentcolor" stroke-width="8">
			<rect x="5" y="5" rx="5" width="37.5" height="37.5" />
			<rect x="5" y="57.5" rx="5" width="37.5" height="37.5" />
			<rect x="57.5" y="57.5" rx="5" width="37.5" height="37.5" />
			<path d="M61.5 24h30m-15-15v30" stroke-linecap="round" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/color-game/"
		title="Color Game"
		description="A game to improve the players ability to determine the color a hex, rgb or hsl value represents, or vice versa."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/cobweb/"
		title="Cobweb Diagram Visualizer"
		description="A tool to plot cobweb diagrams for discrete dynamical systems."
	>
		<svg viewBox="0 0 100 100" fill="none" stroke="currentcolor" stroke-linecap="round">
			<path
				d="M27.387 84.977l7.283-9.353m43.216-55.039L67.691 33.219m21.974 56.789L76.656 79.233M10.335 21.67l8.076 6.161m30.442 69.806l.081-10.294m2.691-84.979l-.674 21.271m8.361 19.849c-2.794-.898-5.761.498-8.867-3.87m8.867 3.87L41.953 66.271m17.359-22.787c-.121 5.117-2.631 12.679 1.269 21.636m-1.269-21.636l8.378-10.265m-17.245 6.395c-6.663 1.534-10.377 2.452-18.387.464m18.387-.464l-.978 30.872m.978-30.872l.506-15.979M32.059 40.078c4.53 16.161 7.068 24.903 9.895 26.194m-9.895-26.193L60.581 65.12M32.059 40.078L18.411 27.831m23.542 38.44c2.306 2.861 4.168 3.129 7.514 4.214m-7.514-4.214l-7.283 9.353m14.798-5.139c6.017-.966 8.217-2.298 11.113-5.366m-11.113 5.366l-.534 16.857M60.581 65.12l16.075 14.114m0 0c-5.951-15.056-8.428-24.518-8.966-46.015m8.966 46.015c-16.849 6.956-21.102 7.587-27.722 8.109m18.757-54.123c-7.769-1.856-11.913-3.221-16.739-9.585m0 0c-13.01 5.922-25.141 5.303-32.54 4.196m0 0c3.97 18.68 10.684 33.648 16.259 47.794m0 0c6.691 8.311 9.794 10.873 14.264 11.718"
				stroke-width="4"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/Truth-table-generator"
		title="Truth Table Generator"
		description="A CLI tool to generate truth tables for logical propositions. I made this in first year to cheese an assignment."
	>
		<svg viewBox="0 0 100 100" stroke="currentcolor" stroke-width="8" stroke-linejoin="round">
			<path d="M10 15h80v70h-80zM10 35h80M30 35v50M50 35v50M70 35v50" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/Imerge"
		title="Imerge*"
		description="A tool to create images that emerge through an exponentially splitting cell."
	>
		<svg viewBox="0 0 100 100" fill="currentcolor">
			<circle cx="12.5" cy="12.5" r="12.5" />
			<circle cx="37.5" cy="12.5" r="12.5" />
			<circle cx="12.5" cy="37.5" r="12.5" />
			<circle cx="37.5" cy="37.5" r="12.5" />
			<circle cx="75" cy="25" r="25" />
			<circle cx="25" cy="75" r="25" />
			<circle cx="75" cy="75" r="25" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/edit-list-on-label"
		title="Edit List on Label*"
		description="GitHub action to add/remove issue titles to/from a list in a markdown file in your repo when a label is added/removed."
	>
		<svg viewBox="0 0 24 24" fill="currentcolor">
			<path
				d="M10.984 13.836a.5.5 0 0 1-.353-.146l-.745-.743a.5.5 0 1 1 .706-.708l.392.391l1.181-1.18a.5.5 0 0 1 .708.707l-1.535 1.533a.504.504 0 0 1-.354.146zm9.353-.147l1.534-1.532a.5.5 0 0 0-.707-.707l-1.181 1.18l-.392-.391a.5.5 0 1 0-.706.708l.746.743a.497.497 0 0 0 .706-.001zM4.527 7.452l2.557-1.585A1 1 0 0 0 7.09 4.17L4.533 2.56A1 1 0 0 0 3 3.406v3.196a1.001 1.001 0 0 0 1.527.85zm2.03-2.436L4 6.602V3.406l2.557 1.61zM24 12.5c0 1.93-1.57 3.5-3.5 3.5a3.503 3.503 0 0 1-3.46-3h-2.08a3.503 3.503 0 0 1-3.46 3a3.502 3.502 0 0 1-3.46-3h-.558c-.972 0-1.85-.399-2.482-1.042V17c0 1.654 1.346 3 3 3h.04c.244-1.693 1.7-3 3.46-3c1.93 0 3.5 1.57 3.5 3.5S13.43 24 11.5 24a3.502 3.502 0 0 1-3.46-3H8c-2.206 0-4-1.794-4-4V9.899A5.008 5.008 0 0 1 0 5c0-2.757 2.243-5 5-5s5 2.243 5 5a5.005 5.005 0 0 1-4.952 4.998A2.482 2.482 0 0 0 7.482 12h.558c.244-1.693 1.7-3 3.46-3a3.502 3.502 0 0 1 3.46 3h2.08a3.503 3.503 0 0 1 3.46-3c1.93 0 3.5 1.57 3.5 3.5zm-15 8c0 1.378 1.122 2.5 2.5 2.5s2.5-1.122 2.5-2.5s-1.122-2.5-2.5-2.5S9 19.122 9 20.5zM5 9c2.206 0 4-1.794 4-4S7.206 1 5 1S1 2.794 1 5s1.794 4 4 4zm9 3.5c0-1.378-1.122-2.5-2.5-2.5S9 11.122 9 12.5s1.122 2.5 2.5 2.5s2.5-1.122 2.5-2.5zm9 0c0-1.378-1.122-2.5-2.5-2.5S18 11.122 18 12.5s1.122 2.5 2.5 2.5s2.5-1.122 2.5-2.5zm-13 8a.5.5 0 1 0 1 0a.5.5 0 0 0-1 0zm2 0a.5.5 0 1 0 1 0a.5.5 0 0 0-1 0zm12 0c0 1.93-1.57 3.5-3.5 3.5a3.503 3.503 0 0 1-3.46-3.002c-.007.001-.013.005-.021.005l-.506.017h-.017a.5.5 0 0 1-.016-.999l.506-.017c.018-.002.035.006.052.007A3.503 3.503 0 0 1 20.5 17c1.93 0 3.5 1.57 3.5 3.5zm-1 0c0-1.378-1.122-2.5-2.5-2.5S18 19.122 18 20.5s1.122 2.5 2.5 2.5s2.5-1.122 2.5-2.5z"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/movie-database"
		title="Movie Database*"
		description="A tool to help me build and maintain my database of movies & series I have seen and want to see."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/graph-builder/"
		title="Graph Builder*"
		description="A tool to build directed weighted graphs from input in a specific format as described by CSC2001F."
	>
		<svg viewBox="0 0 100 100" stroke="currentcolor" stroke-width="8">
			<path d="M35 25L50 50L75 35M25 75L50 50L80 70" />
			<circle cx="35" cy="25" r="8" />
			<circle cx="75" cy="35" r="8" />
			<circle cx="50" cy="50" r="8" />
			<circle cx="25" cy="75" r="8" />
			<circle cx="80" cy="70" r="8" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/svg-editor/"
		title="SVG Editor*"
		description="A tool for creating and editing SVGs that I intend to turn into a VS Code extension. & Obsidian plugin."
	>
		<svg viewBox="0 0 18 18" fill="currentcolor" fill-rule="evenodd">
			<path d="M2 0l3.7 18l4.39-6.6l7.45-2zm1.7 2.4l2.6 12.6l3.05-4.62l5.2-1.4z" />
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/automarker"
		title="Offline Automarker*"
		description="An automatic marker to validate the output of java / python console scripts. Intended for UCT assignments."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/object-validator"
		title="Python Object Validator"
		description="A simple tool to validate python dictionaries and/or lists against a schema."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/did-i-dp"
		title="Did I DP?"
		description="A simple tool I threw together for my classmates to check their DP status (UCT CSC3003S 2022)."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/svelte-template"
		title="Svelte Template*"
		description="A tool to scaffold svelte and sveltekit apps."
	>
		<svg viewBox="0 0 24 24" fill="currentcolor">
			<path
				d="M10.354 21.125a4.44 4.44 0 0 1-4.765-1.767a4.109 4.109 0 0 1-.703-3.107a3.898 3.898 0 0 1 .134-.522l.105-.321l.287.21a7.21 7.21 0 0 0 2.186 1.092l.208.063l-.02.208a1.253 1.253 0 0 0 .226.83a1.337 1.337 0 0 0 1.435.533a1.231 1.231 0 0 0 .343-.15l5.59-3.562a1.164 1.164 0 0 0 .524-.778a1.242 1.242 0 0 0-.211-.937a1.338 1.338 0 0 0-1.435-.533a1.23 1.23 0 0 0-.343.15l-2.133 1.36a4.078 4.078 0 0 1-1.135.499a4.44 4.44 0 0 1-4.765-1.766a4.108 4.108 0 0 1-.702-3.108a3.855 3.855 0 0 1 1.742-2.582l5.589-3.563a4.072 4.072 0 0 1 1.135-.499a4.44 4.44 0 0 1 4.765 1.767a4.109 4.109 0 0 1 .703 3.107a3.943 3.943 0 0 1-.134.522l-.105.321l-.286-.21a7.204 7.204 0 0 0-2.187-1.093l-.208-.063l.02-.207a1.255 1.255 0 0 0-.226-.831a1.337 1.337 0 0 0-1.435-.532a1.231 1.231 0 0 0-.343.15L8.62 9.368a1.162 1.162 0 0 0-.524.778a1.24 1.24 0 0 0 .211.937a1.338 1.338 0 0 0 1.435.533a1.235 1.235 0 0 0 .344-.151l2.132-1.36a4.067 4.067 0 0 1 1.135-.498a4.44 4.44 0 0 1 4.765 1.766a4.108 4.108 0 0 1 .702 3.108a3.857 3.857 0 0 1-1.742 2.583l-5.589 3.562a4.072 4.072 0 0 1-1.135.499m10.358-17.95C18.484-.015 14.082-.96 10.9 1.068L5.31 4.63a6.412 6.412 0 0 0-2.896 4.295a6.753 6.753 0 0 0 .666 4.336a6.43 6.43 0 0 0-.96 2.396a6.833 6.833 0 0 0 1.168 5.167c2.229 3.19 6.63 4.135 9.812 2.108l5.59-3.562a6.41 6.41 0 0 0 2.896-4.295a6.756 6.756 0 0 0-.665-4.336a6.429 6.429 0 0 0 .958-2.396a6.831 6.831 0 0 0-1.167-5.168Z"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/vscode-theme"
		title="VS Code Theme*"
		description="My personalized theme for vs code."
	>
		<svg viewBox="0 0 24 24" fill="currentcolor">
			<path
				d="M17 16.47V7.39l-6 4.54M2.22 9.19a.858.858 0 0 1-.02-1.15l1.2-1.11c.2-.18.69-.26 1.05 0l3.42 2.61l7.93-7.25c.32-.32.87-.45 1.5-.12l4 1.91c.36.21.7.54.7 1.15v13.5c0 .4-.29.83-.6 1l-4.4 2.1c-.32.13-.92.01-1.13-.2l-8.02-7.3l-3.4 2.6c-.38.26-.85.19-1.05 0l-1.2-1.1c-.32-.33-.28-.87.05-1.2l3-2.7"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/obsidian-url-into-selection"
		title="Obsidian URL into Selection*"
		description="My fork of an Obsidian plugin that enables pasting links into text, updating it to work with the WYSIWYG editor."
	>
		<svg viewBox="0 0 24 24" fill="currentcolor">
			<path
				d="M15.074 0C12.586 1.374 10.1 2.749 7.613 4.124l.823 4.266l6.365-5.015zm.172.059l-.269 3.314l4.497 2.752zm-.353 3.466L8.487 8.576l7.39 15.367l1.177-2.359L19.58 6.4c-.012-.009-4.688-2.875-4.688-2.875zm-7.425.779l-3.05 6.594L9.033 21.51l-.74-12.934l-.012-.064zm1.025 4.688l.73 12.784L15.71 24Z"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/mikhas-tools"
		title="Mikha's Tools"
		description="A set of hotkeys & hotstrings for making everyday computer tasks faster. My first ever coding project."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://mikhad.github.io/cheepaska-clone/"
		title="Cheepaska Clone*"
		description="A browser clone of the discontinued mobile game Cheepaska by Yiotro."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/banner-generator"
		title="Banner Creator*"
		description="A simple tool to quickly add text to a banner background for making banners within a discord channel."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/Symbol-Insertion-Framework"
		title="Symbol Insertion Framework*"
		description="An extensible symbol insertion system that converts keywords into symbols when they are selected & a hotkey is pressed."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/Zaio-Bootcamp-Stage-1"
		title="Zaio Bootcamp Stage 1"
		description="My stage 1 project for a free student run bootcamp I partially attended during first year."
	>
		<svg viewBox="-10 0 190 190" fill="currentcolor">
			<path
				d="M21.132 173.923l-6.88-1.1c-4.312-.86-12.65-3.152-13.364-3.674-.73-.534-1.016-6.062-.46-8.893 1.3-6.62 4.6-10.814 16.652-21.1 6.805-5.812 10.308-9.286 13.095-12.983 1.672-2.217 4.452-7.328 5.118-9.408.326-1.02.605-1.252 2.2-1.845 5.868-2.18 12.43-2.097 19.266.242 3.568 1.22 4.48 1.663 4.48 2.172 0 .23-.432 1.507-.96 2.835-2.86 7.202-5.82 11.522-15.68 22.898-10.664 12.303-13.993 18.76-14.88 28.864l-.217 2.48-2.453-.035c-1.35-.02-4.013-.223-5.92-.454zm12.912-.983c.01-3.05 1.527-7.965 3.6-11.648 2.266-4.03 5.16-7.98 11.604-15.84 7.75-9.455 10.68-13.638 13.575-19.395 1.028-2.043 2.28-4.974 2.78-6.514l.912-2.8 1.904-.96c3.873-1.955 7.244-6.114 9.604-11.85 1.787-4.344 3.126-9.4 6.422-24.262 4.372-19.7 7.147-30.2 9.1-34.428 1.72-3.713 4.656-5.793 9.242-6.548 1.816-.3 4.02-.303 9.76-.017 10.715.534 14.785-.064 18.994-2.8 2.27-1.47 4.004-3.542 5.557-6.633l1.175-2.338 2 3.428c1.106 1.885 3.88 6.226 6.167 9.646s4.435 6.847 4.775 7.615c1.512 3.418 1.295 7.017-.67 11.127-2.408 5.036-5.8 8.777-16.338 18.063-4.146 3.65-8.532 7.694-9.748 8.986-5.095 5.415-10.197 15.1-17.006 32.3-7.3 18.445-11.108 25.148-18.357 32.32-10.148 10.04-23.244 17.77-36.053 21.28-4.974 1.363-10.763 2.345-15.382 2.6l-3.632.207.005-1.57zm62.084-49.248c1.38-2.816 4.255-9.368 6.4-14.56 6.15-14.948 9.592-21.675 14-27.365 2.586-3.338 6.62-7.284 9.2-9 1.1-.737 1.733-1.357 1.63-1.623-.45-1.177-6.347-10.66-6.627-10.66-1.042 0-7.918 6.196-10.832 9.76-4.2 5.14-9.147 14.114-12.962 23.52-4.4 10.847-8.317 19.486-11.057 24.385l-1.02 1.825 3.96 4.972c3.568 4.48 4 4.917 4.4 4.415.237-.307 1.56-2.86 2.938-5.677zM87 43.648c-2.755-1.13-8.437-2.554-12.667-3.174-5.112-.75-12.75-.53-15.563.447l-2.107.7c-.064 0 .215-1.332.62-2.96s1.042-4.976 1.416-7.44c1.992-13.148 2.342-14.476 4.438-16.858 3.774-4.287 12-5.378 17.868-2.373 1.9.966 3.107 2.25 5.04 5.3 4.887 7.745 8.837 10.517 17.6 12.36 5.322 1.118 12.588 1.276 15.623.34 3.77-1.165 5.617-3.134 5.635-6 .01-1.424-.922-4.182-2.256-6.684-1.947-3.654-4.083-5.46-6.426-5.435-2.782.03-5.906 3.583-9.378 10.67l-2.106 4.3-1.994-.462a22.9 22.9 0 0 1-3.827-1.33l-1.834-.868 2.03-3.04c1.116-1.672 3.305-5.488 4.864-8.48 2.507-4.814 3.1-5.72 5.244-7.866 1.572-1.582 3.08-2.75 4.33-3.36 1.748-.85 2.22-.934 5.28-.934s3.53.082 5.28.937c1.154.563 2.764 1.777 4.04 3.046 1.733 1.725 2.445 2.78 3.908 5.783 3.23 6.63 4.038 11.97 2.444 16.144-1.35 3.534-5.355 6.612-10 7.68-2.613.6-6.502.695-15.12.366-6.024-.23-7.355-.195-9.22.248-4.702 1.115-7.974 3.674-9.865 7.714-.536 1.145-1.07 2.07-1.184 2.054s-1.074-.383-2.13-.816zM32.44 189.88c-10.973-.587-19.425-2.256-24.8-4.897-3.1-1.524-4.696-2.806-5.772-4.64-.752-1.283-1.466-4.65-.987-4.65.116 0 .748.34 1.405.753 1.696 1.07 5.92 2.884 8.92 3.832 3.54 1.118 7.294 1.796 11.66 2.106 4.12.292 15.52-.052 19.974-.602 17.315-2.14 34.382-10.144 48.814-22.9 8.255-7.3 12.436-13.933 20.943-33.28 5.92-13.465 9.257-20.12 12.62-25.178 4.362-6.56 7.35-9.884 15.033-16.716 7.386-6.57 9.727-8.956 12.266-12.506 2.628-3.675 5.03-9.302 5.05-11.827.012-1.664.546-1.483 2.023.686 4.194 6.16 3.532 15.112-1.654 22.34-3 4.18-8.62 9.17-15.862 14.08-8.015 5.433-10.383 7.205-12.715 9.514-4.023 3.984-7.42 9.74-9.873 16.726-1.354 3.858-6.08 19.472-5.935 19.615-.944 3.02-1.743 5.06-4.05 9.834-8.745 14.96-18.924 22.072-37.78 31.126-9.28 3.622-18.958 5.748-29.416 6.462-4.394.3-5.98.318-9.864.1zm31.833-78.114c-2.448-1.248-6.425-2.63-9.435-3.278-6.867-1.48-12.752-1.025-18.64 1.438-.497.208-.56.02-.56-1.663 0-4.065 2.016-6.903 5.655-7.96 3.78-1.1 15.3-.094 22.32 1.948 3.113.906 9.055 3.28 9.332 3.727.364.59-2.728 4.286-4.51 5.394-1.97 1.224-2.447 1.27-4.162.395zM74.68 99.38c-3.193-1.692-12.086-4.01-17.92-4.673-5.59-.635-12.504-.052-14.955 1.26-.956.512-1.176.032-1.176-2.56 0-3.094 1.125-4.833 4.113-6.356 1.102-.516 1.7-.706 2.72-.82.494-.135 1.808-.182 4.627-.252 9.478.087 15.387 1.358 25.424 5.47.3.127.377.527.238 1.4-.23 1.43-1.757 6.422-2.062 6.738-.115.12-.57.025-1.01-.208zm1.44-14.484c-9.5-3.692-22.694-5.025-28.86-2.917-2.3.783-2.3.784-2.476.13-.36-1.346-.152-3.898.422-5.137 1.84-3.974 6.056-5.165 15.4-4.348 6.802.595 12.67 1.958 18.034 4.19 2.167.902 2.47 1.125 2.326 1.716a268.2 268.2 0 0 0-.879 4.12c-.394 1.892-.8 3.423-.9 3.402s-1.48-.542-3.065-1.157zm1.738-14.028c-6.35-2.18-12.958-3.336-19.062-3.336-3.53 0-7.498.623-9.038 1.42-.53.275-1.032.5-1.112.5s-.245-.722-.367-1.605c-.518-3.763 1.424-6.95 5-8.192 3.5-1.215 14.56-.545 21.57 1.305 2.836.75 7.937 2.502 8.72 2.998.314.198.214 1.138-.457 4.314-.472 2.233-.94 4.042-1.04 4.02s-1.993-.663-4.205-1.422zM83.8 57.2c-9.793-3.814-23.293-5.093-29.375-2.782-1.988.756-2.133.608-2.14-2.18-.008-3.135 1.142-4.935 4.155-6.506 1.286-.67 1.953-.763 6.24-.863 7.682-.18 15.372 1.095 22.07 3.66 2.3.884 3.036 1.297 2.9 1.65-.1.26-.605 2.056-1.125 3.994s-.985 3.552-1.035 3.587-.81-.217-1.69-.56z"
			/>
		</svg>
	</MAC.Card>
	<MAC.Card
		href="https://github.com/MikhaD/ico-tools"
		title="ICO Tools*"
		description="A tool to convert an image or group of images to an ico file, to replace icoconvert.com which is no longer online."
	>
		/
	</MAC.Card>
	<MAC.Card
		href=""
		title="MP3 Meta*"
		description="A VS Code extension for adding and editing the meta data of MP3 files."
	>
		/
	</MAC.Card>
	<MAC.Card
		href="./drawing-garden"
		title="Drawing Garden"
		description="A copy of drawing.garden that I made many years ago."
	>
		〰
	</MAC.Card>
</MAC.Container>

<style lang="scss">
	* {
		text-align: center;
	}
	h2 {
		margin-bottom: 0;
	}
	div {
		color: var(--fg-02);
		font-size: 1.4rem;
		margin-block: 1rem 2rem;
	}
	.logo {
		height: 25rem;
		display: block;
		margin: 2rem auto;
		max-width: 100%;
	}

	@media (prefers-reduced-motion: no-preference) {
		#cog {
			animation: cog 4s linear infinite;
			transform-origin: center;
			transform-box: fill-box;
		}
	}

	@keyframes cog {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(90deg);
		}
	}
</style>
