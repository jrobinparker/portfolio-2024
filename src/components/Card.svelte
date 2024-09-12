<script>
	import CardImg from './CardImg.svelte';
	import { onMount } from 'svelte';
	export let text, title, years, company, titleTwo, yearsTwo, idx, link, tech;

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

	const mainTech = [tech[0], tech[1], tech[2]];
	const subTech = tech.slice(3, tech.length);

	const hasSubTech = !!subTech.length;
	const hasSecondTitle = yearsTwo && titleTwo;

	const shuffledColors = COLORS.map((val) => ({ val, sort: Math.random() }))
		.sort((a, b) => a.sort - b.sort)
		.map(({ val }) => val);

	const isOdd = idx % 2 === 1;

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

<div class="card text-green-100 flex flex-row {isOdd ? 'flex-row-reverse' : ''} h-5/6 w-5/6">
	<section
		id="gradient-bg"
		style={meshBg}
		class="w-1/2 h-full p-20 place-items-center grid grid-rows-2 grid-flow-col {isOdd
			? 'rounded-tr-lg rounded-br-lg'
			: 'rounded-tl-lg rounded-bl-lg'}"
	>
			<div class="h-full w-full flex place-content-center place-items-center">
				<CardImg src={mainTech[0]} />
			</div>
			<div class="h-full w-full flex place-content-center place-items-center">
				<CardImg src={mainTech[1]} />
			</div>
			<div class="h-full w-full flex place-content-center place-items-center {!hasSubTech ? 'row-span-2' : ''}">
				<CardImg src={mainTech[2]} />
			</div>

			{#if hasSubTech}
				<div
					class="grid grid-rows-2 grid-flow-col place-items-center justify-between h-full bg-slate-700/50 rounded-lg h-3/4 w-3/4"
				>
					{#each subTech as tech}
						<CardImg src={tech} />
					{/each}
				</div>
			{/if}
	</section>
	<section
		class="text-left text-xl w-1/2 h-full box-border px-20 pt-14 place-items-center leading-relaxed text-bg {isOdd
			? 'rounded-tl-lg rounded-bl-lg'
			: 'rounded-tr-lg rounded-br-lg'}"
	>
		<h1 class="text-4xl md:text-3xl font-weight-bold mb-2">
			{company}
		</h1>
		<h2 class="text-3xl md:text-2xl font-weight-semibold">
			{title} <a href={link} target="_blank"><i class="fa-solid fa-link"></i></a>
		</h2>
		<h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{years}</h2>
		{#if hasSecondTitle}
		<h2 class="text-3xl md:text-2xl font-weight-semibold">
			{titleTwo}
		</h2>
		<h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{yearsTwo}</h2>
		{/if}
		<p class="text-xl">
			{text}

			Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum non ligula felis.
			Phasellus ut leo tellus. Nullam nec ipsum quis tortor venenatis eleifend. Mauris lobortis,
			augue quis placerat lacinia, eros ante tincidunt odio, vel blandit tortor est non mauris.
			Fusce condimentum scelerisque velit, a ultrices ligula semper non. Morbi pellentesque semper
			dolor, et viverra odio aliquam eget. Ut mollis scelerisque suscipit. Phasellus posuere lorem
			ac mollis porta. Aenean nibh urna, maximus nec lobortis ac, lacinia ac eros. Duis vel elit
			leo. Phasellus ut ligula felis.
		</p>
	</section>
</div>

<style>
	#gradient-bg {
		background: hsl(227deg, 35%, 80%);
	}

	.text-bg {
		background-color: rgb(36, 39, 58);
	}

	h1 {
		font-weight: 700;
	}

	h2 {
		font-weight: 600;
	}
</style>
