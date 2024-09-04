<script>
    import ActionButton from '../components/ActionButton.svelte'

    const gitHub = {
        icon: '',
        text: 'GitHub',
        url: '#'
    };

    const linkedIn = {
        icon: '',
        text: 'LinkedIn',
        url: '#'
    };

    const about = {
        icon: '',
        text: 'About Me',
        url: '#'
    };

    const experience = {
        icon: '',
        text: 'Experience',
        url: '#'
    };

    const actionIcons = [gitHub, linkedIn, about, experience];
</script>

<main class="flex min-h-screen overflow-x-hidden flex-col items-center justify-start">
	<div
		class="relative mx-auto min-h-screen flex justify-center flex-col max-w-7xl px-6 text-center md:px-8"
	>
		<h1
			class="page-title text-center text-9xl text-zinc-50 -translate-y-4 text-balance"
		>
			Jeremy Parker
		</h1>
		<div class="grid grid-cols-2 gap-x-0 gap-y-4 w-1/2 self-center place-items-center mt-20">
            {#each actionIcons as icon}
                <ActionButton text={icon.text} />
			{/each}
		</div>
	</div>
</main>

<style>
	.page-title {
		font-weight: 700;
	}
	.menu div {
		margin-top: 10%;
		margin-bottom: 10%;
	}
</style>
