<script>
	import CardImg from './CardImg.svelte';

	import agImg from '$lib/agricultural-workers.webp';
	import tailwindLogo from '$lib/tailwind-logo.svg';
	import typeScriptLogo from '$lib/typescript-logo.png';
	import { onMount } from 'svelte';

	export let text;
	export let title;
	export let subtitle;
	export let idx;
	export let link;

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

			meshGradients.push(`radial-gradient(at ${Number(start)}% ${Number(end)}%, ${shuffledColors[i]} 0px, transparent 50%)`);
		}

		meshBg = `background-image: ${meshGradients.join(', ')};`;
	});
</script>

<div class="card text-green-100 flex flex-row {isOdd ? 'flex-row-reverse' : ''} h-full w-5/6">
	<section
		id="gradient-bg"
		style={meshBg}
		class="w-1/2 h-full p-20 place-items-center {isOdd
			? 'rounded-tr-lg rounded-br-lg'
			: 'rounded-tl-lg rounded-bl-lg'}"
	>
		<div class="flex flex-col h-full logos-bg -mt-5 rounded-lg drop-shadow-lg">
			<img src={agImg} alt="tractor" class="rounded-t-lg h-2/3 aspect-auto" />
			<div class="grid grid-cols-3 h-1/3 gap-6 p-10 place-items-center place-content-evenly">
				<CardImg src={'fa-js'} />
				<CardImg src={'fa-ember'} />
				<CardImg src={tailwindLogo} />
				<CardImg src={typeScriptLogo} />
				<CardImg src={'fa-react'} />
				<CardImg src={'fa-bootstrap'} />
			</div>
		</div>
	</section>
	<section
		class="text-left text-xl w-1/2 h-full box-border px-20 pt-14 place-items-center leading-relaxed text-bg {isOdd
			? 'rounded-tl-lg rounded-bl-lg'
			: 'rounded-tr-lg rounded-br-lg'}"
	>
		<h1 class="text-4xl font-weight-bold mb-2">
			{title} <a href={link} target="_blank"><i class="fa-solid fa-link"></i></a>
		</h1>
		<h2 class="text-3xl font-weight-semibold">{subtitle}</h2>
		<h2 class="text-2xl font-weight-semibold mb-5">2021 - 2022</h2>
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

	.logos-bg {
		background-color: rgb(54, 58, 79);
	}

	h1 {
		font-weight: 700;
	}

	h2 {
		font-weight: 600;
	}
</style>
