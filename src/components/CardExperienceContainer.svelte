<script>
	export let exp, isOdd;

	const hasSecondTitle = exp.yearsTwo && exp.titleTwo;
</script>

<section
	class="text-left text-xl w-1/2 h-full px-20 pt-14 leading-relaxed text-bg {isOdd
		? 'rounded-tl-lg rounded-bl-lg'
		: 'rounded-tr-lg rounded-br-lg'}"
>
	<h1 class="text-4xl md:text-3xl font-weight-bold mb-5">
		{exp.company} <a href={exp.link} target="_blank"><i class="fa-solid fa-link"></i></a>
	</h1>
    <div class:multiple-roles={hasSecondTitle}>
        <div>
            <h2 class="text-3xl md:text-2xl font-weight-semibold">
                {exp.title}
            </h2>
            <h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{exp.years}</h2>
        </div>
        
        {#if hasSecondTitle}
            <div>
                <h2 class="text-3xl md:text-2xl font-weight-semibold">
                    {exp.titleTwo}
                </h2>
                <h2 class="text-2xl md:text-xl font-weight-semibold mb-5">{exp.yearsTwo}</h2>
            </div>
        {/if}
    </div>
	<p class="text-xl mb-5">
		{exp.about}
	</p>
    <p class="text-xl italic mb-5">
        Some of my highlights at {exp.company}:
    </p>
    <ul class="list-disc pl-10">
        {#each exp.accomplishments as accomp}
            <li>{accomp}</li>
        {/each}
    </ul>
</section>

<style lang="scss">
	.text-bg {
		background-color: rgb(36, 39, 58);
	}

    .multiple-roles {
        @apply flex;

        h2:first-of-type {
            @apply mr-5;
        }
    }
</style>
