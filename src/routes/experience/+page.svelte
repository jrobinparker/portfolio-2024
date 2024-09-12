<script lang="ts">
	import ExperienceCard from '../../components/ExperienceCard.svelte';
	import ExperienceContainer from '../../components/ExperienceContainer.svelte';
    import experienceList from '$lib/experienceList';
</script>

<section class="h-5/6">
    <h1 class="text-5xl text-zinc-50 text-balance section-header">Experience</h1>
    <div class="h-full w-full py-10">
        {#each experienceList as exp, idx}
                <div class="w-full h-full mb-40">
                    <ExperienceContainer>
                        <ExperienceCard
                            idx={idx}
                            exp={exp}
                        />
                    </ExperienceContainer>
                </div>
        {/each}
    </div>
</section>


<style>
    .section-header {
        font-family: 'Inter Black';
    }
</style>