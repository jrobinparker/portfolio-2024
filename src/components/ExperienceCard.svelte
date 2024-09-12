<script>
	import CardExperienceContainer from './CardExperienceContainer.svelte';
	import CardIconContainer from './CardIconContainer.svelte';
	export let idx, exp;

	const isOdd = idx % 2 === 1;
</script>

<div class="card text-green-100 flex flex-row {isOdd ? 'flex-row-reverse' : ''} h-5/6 w-5/6">
	<CardIconContainer tech={exp.tech} isOdd={isOdd} />
	<CardExperienceContainer exp={exp} isOdd={isOdd} />
</div>
