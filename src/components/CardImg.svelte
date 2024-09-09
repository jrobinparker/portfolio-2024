<script>
	export let src;
	const tailwindSticker = src.includes('tailwind');
    const typeScriptSticker = src.includes('typescript');
</script>

<div
	class:tailwind-sticker={tailwindSticker}
    class:ts-sticker={typeScriptSticker}
    class="sticker"
>
	{#if (tailwindSticker || typeScriptSticker)}
		<img src={src} />
	{:else}
		<i class="text-4xl fa-brands {src}"></i>
	{/if}
</div>

<style>
	svg {
		color: 'red';
	}

    .sticker { 
        max-width: 75px;
    }

    .large-sticker {
        max-width: 40%;
    }

	.ember-sticker {
        max-width: 100px;
	}

	.tailwind-sticker {
		padding: 10px;
	}

    .ts-sticker {
        max-width: 50px;
    }

	.js-sticker {
		max-width: 50px;
	}

</style>
