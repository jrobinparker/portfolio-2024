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
        url: '/about'
    };

    const experience = {
        icon: '',
        text: 'Experience',
        url: '#'
    };

    const actionIcons = [gitHub, linkedIn, about, experience];
</script>


<h1
    class="page-title text-center text-9xl text-zinc-50 text-balance"
>
    Jeremy Parker
</h1>
<div class="grid grid-cols-2 gap-x-0 gap-y-4 w-1/2 self-center place-items-center mt-20">
    {#each actionIcons as icon}
        <ActionButton text={icon.text} url={icon.url} />
    {/each}
</div>

<style>
	.page-title {
		font-weight: 700;
	}
</style>
