<script lang="ts">
	import CardExperienceContainer from './CardExperienceContainer.svelte';
	import CardIconContainer from './CardIconContainer.svelte';
	import { inview } from 'svelte-inview';
	import type { ObserverEventDetails, ScrollDirection, Options } from 'svelte-inview';
	export let idx, exp;

	const isOdd = idx % 2 === 1;

	let isInView: boolean;

	const options: Options = {
		rootMargin: '-200px',
		unobserveOnEnter: true
	};

	const handleChange = ({ detail }: CustomEvent<ObserverEventDetails>) => {
		isInView = detail.inView;
	};
</script>

<div
	use:inview={options}
	on:inview_change={handleChange}
	class:fade-in-bottom={isInView}
	class:reverse={isOdd}
	class="card text-green-100 flex flex-row opacity-0 h-5/6 w-5/6"
>
	<CardIconContainer tech={exp.tech} {isOdd} />
	<CardExperienceContainer {exp} {isOdd} />
</div>

<style lang="postcss">
	.reverse {
		@apply flex-row-reverse;
	}

	.fade-in-bottom {
		-webkit-animation: fade-in-bottom 0.6s cubic-bezier(0.39, 0.575, 0.565, 1) both;
		-moz-animation: fade-in-bottom 0.6s cubic-bezier(0.39, 0.575, 0.565, 1) both;
		animation: fade-in-bottom 0.6s cubic-bezier(0.39, 0.575, 0.565, 1) both;
	}

	@-webkit-keyframes fade-in-bottom {
		0% {
			-webkit-transform: translateY(50px);
			transform: translateY(50px);
			opacity: 0;
		}
		100% {
			-webkit-transform: translateY(0);
			transform: translateY(0);
			opacity: 1;
		}
	}

	@-moz-keyframes fade-in-bottom {
		0% {
			-webkit-transform: translateY(50px);
			transform: translateY(50px);
			opacity: 0;
		}
		100% {
			-webkit-transform: translateY(0);
			transform: translateY(0);
			opacity: 1;
		}
	}

	@keyframes fade-in-bottom {
		0% {
			-webkit-transform: translateY(50px);
			transform: translateY(50px);
			opacity: 0;
		}
		100% {
			-webkit-transform: translateY(0);
			transform: translateY(0);
			opacity: 1;
		}
	}
</style>
