<script>
	export let src;

	const sm = src.includes('apple') || src.includes('rails');
	const med = src.includes('js') || src.includes('python') || src.includes('react') || src.includes('ts') || src.includes('jira');
	const lg = src.includes('php') || src.includes('tailwind');
	const sentry = src.includes('sentry');
</script>

<div
	class:sm={sm}
	class:med={med}
	class:lg={lg}
	class:sentry={sentry}
>
	<img {src} alt={src} />
</div>

<style lang="scss">
	.sm {
		width: 40%;
	}

    .med {
		img {
			border-radius: 5%;
		}

        width: 60%;
    }

	.lg {
		width: 70%;
	}

	.sentry {
		fill: white;
		width: 45%;
	}
</style>
