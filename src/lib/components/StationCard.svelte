<script lang="ts">
    const roundel = "/Underground_(no_text).svg";

    let {
        original,
        wordplay,
        flipped = $bindable(false),
    }: { original: string; wordplay: string; flipped?: boolean } = $props();
</script>

<button
    class="card"
    class:flipped
    onclick={() => (flipped = !flipped)}
    aria-pressed={flipped}
    aria-label={flipped
        ? `${wordplay}. Click to show original name.`
        : `${original}. Click to reveal heatwave name.`}
>
    <span class="card-inner">
        <span class="face front">
            <img class="roundel" src={roundel} alt="" />
            <span class="name">{original}</span>
        </span>

        <span class="face back">
            <span class="fire" aria-hidden="true">🔥</span>
            <img class="roundel" src={roundel} alt="" />
            <span class="name">{wordplay}</span>
        </span>
    </span>
</button>

<style>
    .card {
        position: relative;
        display: block;
        width: 100%;
        aspect-ratio: 3 / 2.2;
        padding: 0;
        border: none;
        background: none;
        cursor: pointer;
        perspective: 1000px;
        font: inherit;
        color: inherit;
        opacity: 90%;
    }

    .card-inner {
        position: relative;
        display: block;
        width: 100%;
        height: 100%;
        transform-style: preserve-3d;
        transition: transform 0.6s cubic-bezier(0.4, 0.2, 0.2, 1);
    }

    .card.flipped .card-inner {
        transform: rotateY(180deg);
    }

    .face {
        position: absolute;
        inset: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 0.5rem;
        padding: 0.75rem;
        border-radius: 5px;
        backface-visibility: hidden;
        box-shadow: 0 1px 3px rgba(0, 0, 0, 0.25);
    }

    .front {
        background: #f2efe9;
    }

    .back {
        background: #ffe79e;
        transform: rotateY(180deg);
    }

    .roundel {
        width: 4.5rem;
        height: auto;
    }

    .name {
        text-align: center;
        font-family: "Inter", "Helvetica Neue", Arial, sans-serif;
        font-weight: 400;
        font-size: 1rem;
        line-height: 1.2;
        color: #0e1316;
    }

    .fire {
        position: absolute;
        top: 0.5rem;
        right: 0.5rem;
        font-size: 1.25rem;
        line-height: 1;
    }
</style>
