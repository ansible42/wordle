<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the <strong>WORDLE</strong> in {ROWS} tries. All answers are food themed.</div>
<div>Each guess must be a valid {COLS} letter word. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	word.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Examples</strong></div>
	<div class="row">
		<Tile value="l" state="🟩" />
		<Tile value="o" state="🔳" />
		<Tile value="c" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="l" state="🔳" />
	</div>
	<div>The letter <strong>W</strong> is in the word and in the correct spot.</div>
	<div class="row">
		<Tile value="t" state="🔳" />
		<Tile value="a" state="🟨" />
		<Tile value="s" state="🔳" />
		<Tile value="t" state="🔳" />
		<Tile value="y" state="🔳" />
	</div>
	<div>The letter <strong>I</strong> is in the word but in the wrong spot.</div>
	<div class="row">
		<Tile value="s" state="🔳" />
		<Tile value="n" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="c" state="⬛" />
		<Tile value="k" state="🔳" />
	</div>
	<div>The letter <strong>U</strong> is not in the word in any spot.</div>
	<div>All ansers are food or farm realated.</div>
	<a href="https://seattlefarmersmarkets.org/">
		<img src="img/NFM-logo-no-background.gif" alt="NFM" style="width:40%">
	  </a> 
</div>


<div>

	<br /> <br />
	Open the settings menu to see some of the additional features.
	<br/> <br/>
	This is a recreation of the original <a
		href="https://www.powerlanguage.co.uk/wordle/"
		target="_blank">Wordle</a
	>
	by Josh Wardle with additional modes and features. Written with Svelte, in Typescript by
	<a href="https://github.com/MikhaD" target="_blank">MikhaD</a>. 
	Modifed by <a href="https://github.com/ansible42" target="_blank">Ansible42</a> 
	for NFM unter <a href="https://github.com/ansible42/wordle/blob/main/LICENSE">MIT license</a>. 
	<br/><br/>
	<a href="https://ansible42.github.io/wordle/" ><img src="https://github.com/ansible42/wordle/workflows/Publish/badge.svg?branch=main" alt="Publish workflow"/></a>	

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
