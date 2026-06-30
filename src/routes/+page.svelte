<script lang="ts">
    import StationCard from "$lib/components/StationCard.svelte";
    import stationsData from "$lib/stations.json";

    function shuffle<T>(items: T[]): T[] {
        const result = [...items];
        for (let i = result.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [result[i], result[j]] = [result[j], result[i]];
        }
        return result;
    }

    const stations = shuffle(stationsData);

    let allFlipped = $state(false);
    let flippedStates = $state(stations.map(() => false));

    function toggleAll() {
        allFlipped = !allFlipped;
        flippedStates = stations.map(() => allFlipped);
    }
</script>

<div class="toolbar">
    <button class="toggle-all" onclick={toggleAll}>
        {allFlipped ? "Show original names" : "Show heatwave names"}
    </button>
</div>

<main class="grid">
    {#each stations as station, i (station.original)}
        <StationCard
            original={station.original}
            wordplay={station.wordplay}
            bind:flipped={flippedStates[i]}
        />
    {/each}
</main>

<style>
    .toolbar {
        display: flex;
        justify-content: flex-end;
        padding: 1.5rem 1.5rem 0;
    }

    .toggle-all {
        padding: 0.6rem 1.25rem;
        border: none;
        border-radius: 0.5rem;
        background: #0e1316;
        color: #f2efe9;
        font-family: "Archivo Narrow", "Helvetica Neue", Arial, sans-serif;
        font-weight: 700;
        font-size: 0.9rem;
        letter-spacing: 0.03em;
        text-transform: uppercase;
        cursor: pointer;
        transition: background 0.15s ease;
    }

    .toggle-all:hover,
    .toggle-all:focus-visible {
        background: #006fc0;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
        gap: 1.5rem;
        padding: 1rem;
    }
</style>
