<script>
	import { onMount } from 'svelte';
	import CardIcon from './CardIcon.svelte';
	export let tech, isOdd;

	const mainTech = [tech[0], tech[1], tech[2]];
	const subTech = tech.slice(3, tech.length);

	const hasSubTech = !!subTech.length;

	const COLORS = [
		'hsl(10deg, 56%, 91%)',
		'hsl(0deg, 59%, 88%)',
		'hsl(316deg, 72%, 86%)',
		'hsl(267deg, 84%, 81%)',
		'hsl(343deg, 81%, 75%)',
		'hsl(350deg, 65%, 77%)',
		'hsl(23deg, 92%, 75%)',
		'hsl(41deg, 86%, 83%)',
		'hsl(115deg, 54%, 76%)',
		'hsl(170deg, 57%, 73%)',
		'hsl(189deg, 71%, 73%)',
		'hsl(199deg, 76%, 69%)',
		'hsl(217deg, 92%, 76%)',
		'hsl(232deg, 97%, 85%)'
	];

	const shuffledColors = COLORS.map((val) => ({ val, sort: Math.random() }))
		.sort((a, b) => a.sort - b.sort)
		.map(({ val }) => val);

	let meshBg = '';

	onMount(() => {
		const gradientBg = document.getElementById('gradient-bg');

		if (!gradientBg) return;

		const randomNumOfLayers = Math.floor(Math.random() * 6) + 1;
		const meshGradients = [];

		for (let i = 0; i < randomNumOfLayers; i++) {
			const start = Math.floor(Math.random() * 100);
			const end = Math.floor(Math.random() * 100);

			meshGradients.push(
				`radial-gradient(at ${Number(start)}% ${Number(end)}%, ${shuffledColors[i]} 0px, transparent 50%)`
			);
		}

		meshBg = `background-image: ${meshGradients.join(', ')};`;
	});
</script>

<section
	id="gradient-bg"
	style={meshBg}
	class="w-1/2 h-full p-20 place-items-center grid grid-rows-2 grid-flow-col {isOdd
		? 'rounded-tr-lg rounded-br-lg'
		: 'rounded-tl-lg rounded-bl-lg'}"
>
	<div class="h-full w-full flex place-content-center place-items-center">
		<CardIcon src={mainTech[0]} />
	</div>
	<div class="h-full w-full flex place-content-center place-items-center">
		<CardIcon src={mainTech[1]} />
	</div>
	<div
		class="h-full w-full flex place-content-center place-items-center {!hasSubTech
			? 'row-span-2'
			: ''}"
	>
		<CardIcon src={mainTech[2]} />
	</div>

	{#if hasSubTech}
		<div
			class="grid grid-rows-2 grid-flow-col place-items-center justify-between bg-slate-700/50 rounded-lg h-3/4 w-3/4"
		>
			{#each subTech as tech}
				<CardIcon src={tech} />
			{/each}
		</div>
	{/if}
</section>

<style>
	#gradient-bg {
		background: hsl(227deg, 35%, 80%);
	}
</style>
