<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the <strong>WORDLE</strong> in {ROWS} tries.</div>
<div>Each guess must be a valid {COLS} letter word. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	word.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Examples</strong></div>
	<div class="row">
		<Tile value="w" state="🟩" />
		<Tile value="a" state="🔳" />
		<Tile value="g" state="🔳" />
		<Tile value="e" state="🔳" />
		<Tile value="r" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="n" state="🔳" />
		<Tile value="g" state="🔳" />
	</div>
	<div>The letter <strong>W</strong> is in the word and in the correct spot.</div>
	<div class="row">
		<Tile value="p" state="🔳" />
		<Tile value="a" state="🟨" />
		<Tile value="c" state="🔳" />
		<Tile value="k" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="g" state="🔳" />
		<Tile value="e" state="🔳" />
		<Tile value="r" state="🔳" />
	</div>
	<div>The letter <strong>A</strong> is in the word but in the wrong spot.</div>
	<div class="row">
		<Tile value="v" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="c" state="⬛" />
		<Tile value="a" state="🔳" />
		<Tile value="t" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="o" state="🔳" />
		<Tile value="n" state="🔳" />
	</div>
	<div>The letter <strong>C</strong> is not in the word in any spot.</div>
</div>
<div>
	This is a fork of a recreation of the original <a
		href="https://www.nytimes.com/games/wordle/"
		target="_blank">Wordle</a
	>
	by Josh Wardle with additional features, for Kaileb's Exhibition. Enjoy!
	<br /><br />
	Open the settings menu to see some of the additional features.
	<br />
	Written with Svelte, in Typescript by
	<a href="https://github.com/KailebAylett" target="_blank">Kaileb Aylett</a>.
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
