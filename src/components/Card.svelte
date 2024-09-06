<script>
	import CardImg from './CardImg.svelte';

	import agImg from '$lib/agricultural-workers.webp';
	import emberLogo from '$lib/ember-logo.svg';
	import jsLogo from '$lib/js-logo.png';
	import reactNativeLogo from '$lib/react-native-logo.svg';
	import bootstrapLogo from '$lib/bootstrap-logo.png';
	import tailwindLogo from '$lib/tailwind-logo.svg';
	import typeScriptLogo from '$lib/typescript-logo.png';

	export let text;
	export let title;
	export let subtitle;
	export let idx;

	const isOdd = idx % 2 === 1;
</script>

<div class="card text-green-100 flex flex-row {isOdd ? 'flex-row-reverse' : ''} h-full w-5/6">
	<section class="w-1/2 h-full gradient-bg p-20 place-items-center {isOdd ? 'rounded-tr-lg rounded-br-lg' : 'rounded-tl-lg rounded-bl-lg'}">
		<div class="flex flex-col bg-slate-700 -mt-5 my-auto rounded-lg drop-shadow-lg">
			<img src={agImg} alt="tractor" class="rounded-t-lg" />
			<div class="grid grid-cols-3 gap-6 p-10 place-items-center place-content-evenly">
				<CardImg src={jsLogo} />
				<CardImg src={emberLogo} />
				<CardImg src={tailwindLogo} />
				<CardImg src={typeScriptLogo} />
				<CardImg src={reactNativeLogo} />
				<CardImg src={bootstrapLogo} />
			</div>
		</div>
	</section>
	<section class="text-left text-xl w-1/2 h-full px-20 pt-14 place-items-center leading-relaxed experience-text {isOdd ? 'rounded-tl-lg rounded-bl-lg' : 'rounded-tr-lg rounded-br-lg'}">
		<h1 class="text-4xl font-weight-bold mb-2">{title} <a href="#">link</a></h1>
		<h2 class="text-3xl font-weight-semibold">{subtitle}</h2>
		<h2 class="text-2xl font-weight-semibold mb-5">2021 - 2022</h2>
		<p>
			{text}

			Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum non ligula felis. Phasellus
			ut leo tellus. Nullam nec ipsum quis tortor venenatis eleifend. Mauris lobortis, augue quis
			placerat lacinia, eros ante tincidunt odio, vel blandit tortor est non mauris. Fusce condimentum
			scelerisque velit, a ultrices ligula semper non. Morbi pellentesque semper dolor, et viverra
			odio aliquam eget. Ut mollis scelerisque suscipit. Phasellus posuere lorem ac mollis porta.
			Aenean nibh urna, maximus nec lobortis ac, lacinia ac eros. Duis vel elit leo. Phasellus ut
			ligula felis.
		</p>

	</section>
</div>

<style>
	.gradient-bg {
		background: hsla(141, 54%, 86%, 1);

		background: linear-gradient(
			90deg,
			hsla(141, 54%, 86%, 1) 0%,
			hsla(333, 73%, 85%, 1) 50%,
			hsla(211, 58%, 79%, 1) 100%
		);

		background: -moz-linear-gradient(
			90deg,
			hsla(141, 54%, 86%, 1) 0%,
			hsla(333, 73%, 85%, 1) 50%,
			hsla(211, 58%, 79%, 1) 100%
		);

		background: -webkit-linear-gradient(
			90deg,
			hsla(141, 54%, 86%, 1) 0%,
			hsla(333, 73%, 85%, 1) 50%,
			hsla(211, 58%, 79%, 1) 100%
		);
	}

	.experience-text {
		background-color: rgb(54, 58, 79);
	}

	h1 {
		font-weight: 700;
	}

	h2 {
		font-weight: 600;
	}
</style>
