<script>
	export let src;

	const emberSticker = src.includes('ember');
	const tailwindSticker = src.includes('tailwind');
	const javaScript = src.includes('js') || src.includes('i18n');
    const typeScriptSticker = src.includes('typescript');
    const largeSticker = src.includes('qunit');
</script>

<div
	class:ember-sticker={emberSticker}
	class:tailwind-sticker={tailwindSticker}
	class:js-sticker={javaScript}
    class:ts-sticker={typeScriptSticker}
    class:large-sticker={largeSticker}
    class="sticker"
>
	<img {src} alt="ember-logo" />
</div>

<style>

    .sticker { 
        max-width: 50%;
    }

    .large-sticker {
        max-width: 40%;
    }

	.ember-sticker {
        max-width: 70%;
	}

	.tailwind-sticker {
		padding: 10px;
	}

    .ts-sticker {
        max-width: 100%;
    }

	.js-sticker {
		max-width: 35%;

	}

</style>
