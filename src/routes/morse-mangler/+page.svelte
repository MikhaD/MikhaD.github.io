<script>
	import "./style.css";
	import JS from "./script.js";
	import favicon from "./favicon.png";
	import { onMount } from "svelte";

	onMount(JS);
</script>

<svelte:head>
	<link rel="shortcut icon" href={favicon} type="image/x-icon" />
	<title>Morse Mangler</title>
</svelte:head>

<header class="header">
	<h1>Mikha's Morse Mangler</h1>
</header>
<section class="text">
	<div class="card">
		<section class="side front">
			<div class="textarea">
				<h2>Morse</h2>
				<textarea id="input-morse" />
			</div>
			<div class="textarea">
				<div class="h2">
					<h2>English</h2>
					<span class="copy" id="copy-english">📋</span>
				</div>
				<textarea id="output-english" readonly />
			</div>
		</section>
		<section class="side back">
			<div class="textarea">
				<h2>English</h2>
				<textarea id="input-english" />
			</div>
			<div class="textarea">
				<div class="h2">
					<h2>Morse</h2>
					<span class="copy" id="copy-morse">📋</span>
				</div>
				<textarea id="output-morse" readonly />
			</div>
		</section>
	</div>
</section>
<section class="controls">
	<div class="buttons">
		<button id="translate">Translate</button>
		<button id="switch" class="">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 524 524" fill="#fff">
				<path
					d="M370.146 93.732c-96.335 3.505-175.286 75.145-190.1 168.167l61.723-.001-120.753 137.02L.265 261.898 62 261.9C62.055 151.488 151.577 62 262 62c39.843 0 76.965 11.65 108.145 31.732zM523.735 262.1L402.982 125.08 282.23 262.1h61.723c-14.813 93.022-93.764 164.662-190.1 168.167C185.033 450.35 222.156 462 262 462c110.423 0 199.946-89.488 200-199.9h61.735z"
				/>
			</svg>
		</button>
	</div>
	<div class="checkboxes">
		<div id="slashSep" class="checkbox">Words seperated with /</div>
		<div id="unChars" class="checkbox">Translate unknown characters to #</div>
		<div id="extraSpaces" class="checkbox">Raiden Filter</div>
	</div>
</section>
<aside id="code-sheet">
	<div class="up">‹</div>
	<h1>International Morse</h1>
	<span class="close">×</span>
	<div class="table">
		<div class="column">
			<div class="row">
				<div class="char">A</div>
				<div class="morse">.-</div>
			</div>
			<div class="row">
				<div class="char">B</div>
				<div class="morse">-...</div>
			</div>
			<div class="row">
				<div class="char">C</div>
				<div class="morse">-.-.</div>
			</div>
			<div class="row">
				<div class="char">D</div>
				<div class="morse">-..</div>
			</div>
			<div class="row">
				<div class="char">E</div>
				<div class="morse">.</div>
			</div>
			<div class="row">
				<div class="char">F</div>
				<div class="morse">..-.</div>
			</div>
			<div class="row">
				<div class="char">G</div>
				<div class="morse">--.</div>
			</div>
			<div class="row">
				<div class="char">H</div>
				<div class="morse">....</div>
			</div>
			<div class="row">
				<div class="char">I</div>
				<div class="morse">..</div>
			</div>
			<div class="row">
				<div class="char">J</div>
				<div class="morse">.---</div>
			</div>
			<div class="row">
				<div class="char">K</div>
				<div class="morse">-.-</div>
			</div>
			<div class="row">
				<div class="char">L</div>
				<div class="morse">.-..</div>
			</div>
			<div class="row">
				<div class="char">M</div>
				<div class="morse">--</div>
			</div>
			<div class="row">
				<div class="char">N</div>
				<div class="morse">-.</div>
			</div>
			<div class="row">
				<div class="char">O</div>
				<div class="morse">-.</div>
			</div>
			<div class="row">
				<div class="char">P</div>
				<div class="morse">.--.</div>
			</div>
			<div class="row">
				<div class="char">Q</div>
				<div class="morse">--.-</div>
			</div>
			<div class="row">
				<div class="char">R</div>
				<div class="morse">.-.</div>
			</div>
			<div class="row">
				<div class="char">S</div>
				<div class="morse">...</div>
			</div>
			<div class="row">
				<div class="char">T</div>
				<div class="morse">-</div>
			</div>
			<div class="row">
				<div class="char">U</div>
				<div class="morse">..-</div>
			</div>
		</div>
		<div class="column">
			<div class="row">
				<div class="char">V</div>
				<div class="morse">...-</div>
			</div>
			<div class="row">
				<div class="char">W</div>
				<div class="morse">.--</div>
			</div>
			<div class="row">
				<div class="char">X</div>
				<div class="morse">-..-</div>
			</div>
			<div class="row">
				<div class="char">Y</div>
				<div class="morse">-.--</div>
			</div>
			<div class="row">
				<div class="char">Z</div>
				<div class="morse">--..</div>
			</div>
			<div class="row">
				<div class="char">.</div>
				<div class="morse">.-.-.-</div>
			</div>
			<div class="row">
				<div class="char">,</div>
				<div class="morse">--..--</div>
			</div>
			<div class="row">
				<div class="char">?</div>
				<div class="morse">..--..</div>
			</div>
			<div class="row">
				<div class="char">/</div>
				<div class="morse">-..-.</div>
			</div>
			<div class="row">
				<div class="char">@</div>
				<div class="morse">.--.-.</div>
			</div>
			<div class="row">
				<div class="char">1</div>
				<div class="morse">.----</div>
			</div>
			<div class="row">
				<div class="char">2</div>
				<div class="morse">..---</div>
			</div>
			<div class="row">
				<div class="char">3</div>
				<div class="morse">...--</div>
			</div>
			<div class="row">
				<div class="char">4</div>
				<div class="morse">....-</div>
			</div>
			<div class="row">
				<div class="char">5</div>
				<div class="morse">.....</div>
			</div>
			<div class="row">
				<div class="char">6</div>
				<div class="morse">-....</div>
			</div>
			<div class="row">
				<div class="char">7</div>
				<div class="morse">--...</div>
			</div>
			<div class="row">
				<div class="char">8</div>
				<div class="morse">---..</div>
			</div>
			<div class="row">
				<div class="char">9</div>
				<div class="morse">----.</div>
			</div>
			<div class="row">
				<div class="char">0</div>
				<div class="morse">-----</div>
			</div>
		</div>
	</div>
</aside>
