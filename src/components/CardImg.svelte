<script>
	export let src;

	const ember = src.includes('ember') || src.includes('sketch');
	const javaScript = src.includes('js');
	const react = src.includes('react');
	const tailwind = src.includes('tailwind');
    const typeScript = src.includes('ts') || src.includes('jira');
	const python = src.includes('python');
	const sentry = src.includes('sentry');
	const apple = src.includes('apple');
	const php = src.includes('php');
	const rails = src.includes('rails');
</script>

<div
	class:ember={ember}
	class:tailwind={tailwind}
	class:javascript={javaScript}
    class:typescript={typeScript}
	class:react={react}
	class:python={python}
	class:apple={apple}
	class:php={php}
	class:rails={rails}
	class:sentry={sentry}
>
	<img {src} alt="ember-logo" />
</div>

<style>
	.react, .python {
		width: 60%;
	}

	.tailwind {
		width: 70%;
	}

	.sentry {
		fill: white;
		width: 45%;
	}

    .typescript, .javascript {
        width: 60%;
		border-radius: 5%;
    }

	.javascript img {
		border-radius: 5%;
	}
	
	.gh, .sentry {
		@apply text-zinc-50
	}

	.apple, .rails {
		width: 40%;
	}

	.php {
		width: 70%;
	}
</style>
