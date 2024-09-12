<script>
	export let exp, isOdd;

	const hasSecondTitle = exp.yearsTwo && exp.titleTwo;
</script>

<section
	class="text-left text-xl w-1/2 h-full box-border px-20 pt-14 place-items-center leading-relaxed text-bg {isOdd
		? 'rounded-tl-lg rounded-bl-lg'
		: 'rounded-tr-lg rounded-br-lg'}"
>
	<h1 class="text-4xl md:text-3xl font-weight-bold mb-2">
		{exp.company} <a href={exp.link} target="_blank"><i class="fa-solid fa-link"></i></a>
	</h1>
	<h2 class="text-3xl md:text-2xl font-weight-semibold">
		{exp.title}
	</h2>
	<h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{exp.years}</h2>
	{#if hasSecondTitle}
		<h2 class="text-3xl md:text-2xl font-weight-semibold">
			{exp.titleTwo}
		</h2>
		<h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{exp.yearsTwo}</h2>
	{/if}
	<p class="text-xl">
		{exp.about}

		Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum non ligula felis. Phasellus
		ut leo tellus. Nullam nec ipsum quis tortor venenatis eleifend. Mauris lobortis, augue quis
		placerat lacinia, eros ante tincidunt odio, vel blandit tortor est non mauris. Fusce condimentum
		scelerisque velit, a ultrices ligula semper non. Morbi pellentesque semper dolor, et viverra
		odio aliquam eget. Ut mollis scelerisque suscipit. Phasellus posuere lorem ac mollis porta.
		Aenean nibh urna, maximus nec lobortis ac, lacinia ac eros. Duis vel elit leo. Phasellus ut
		ligula felis.
	</p>
</section>

<style>
	.text-bg {
		background-color: rgb(36, 39, 58);
	}
</style>
