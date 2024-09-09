<script lang="ts">
	import Card from '../../components/Card.svelte';
	import ExperienceContainer from '../../components/ExperienceContainer.svelte';
    
    const timelineYears = [2021, 2022, 2023, 2024];

    let selectedYear: number = timelineYears[0];

    function setYear(val: number): void {
        selectedYear = val;
    }
</script>

<section class="h-5/6">
    <h1 class="text-5xl text-zinc-50 text-balance section-header">Experience</h1>
    <div class="h-full w-full py-10">
        {#each timelineYears as year, idx}
            <section class="h-5/6">
                <div class="flex place-content-center items-center self-center w-full h-full mb-10">
                    <ExperienceContainer>
                        <Card
                            idx={idx}
                            title="Telus Agriculture"
                            subtitle="Software Engineer"
                            link="https://www.telus.com/agcg/products/agronomy"
                            text="
                            In 2021, I joined the Web UI team at Telus Agriculture, one of the largest agricultural
                            management platforms in the world and is used daily by over 225,000 large-scale agricultural
                            companies and food distributors. Telus Agriculture's frontend run on Ember, which is notorious
                            for a high learning curve. Learning an extremely complicated, legacy framework helped me grow
                            from a React-only 'frameworker' to a JavaScript engineer."
                        />
                    </ExperienceContainer>
                </div>
            </section>
        {/each}
    </div>
</section>


<style>
    .section-header {
        font-family: 'Inter Black';
    }
</style>