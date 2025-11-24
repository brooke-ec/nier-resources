<script lang="ts">
	let text = $state("Lorem ipsum");

	function resize(e: Event) {
		const area = e.target as HTMLTextAreaElement;
		area.style.height = "auto";
		area.style.height = area.scrollHeight + 5 + "px";
	}
</script>

<div class="container">
	<p class="overlay">{text}</p>
	<textarea oninput={resize} spellcheck="false" bind:value={text}></textarea>
</div>

<style lang="scss">
	@font-face {
		font-family: "AngelicAgrippa";
		src: url("/AngelicAgrippaRegular.otf") format("opentype");
	}

	.container {
		line-height: 45px;
		font-size: 20px;
		position: relative;
		border: 1px solid black;
		border-radius: 5px;
	}

	.overlay {
		position: absolute;
		margin-top: 13px;
		margin-left: 2px;
		white-space: pre-wrap;
		font-family: "AngelicAgrippa";
	}

	textarea {
		width: 100%;
		margin-top: -12px;
		resize: none;
		border: none;
		background: transparent;
		line-height: inherit;
		outline: none;
		inset: 1;
	}
</style>
