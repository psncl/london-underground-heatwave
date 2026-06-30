<script lang="ts">
    import favicon from "$lib/assets/favicon.svg";
    import "../global.css";

    let { children } = $props();
</script>

<svelte:head>
    <link rel="icon" href={favicon} />
</svelte:head>

<div class="container">
    <header class="top-nav">
        <div class="top-nav-title">
            <img
                class="top-nav-logo"
                src="/Underground-with-text.svg"
                alt="London Underground Logo"
            />
            <div>
                <p>
                    The last week of June 2026 was London's hottest in a while.
                </p>
                <p class="top-nav-subtitle">
                    What if the underground stations switched names for the
                    week?
                </p>
            </div>
        </div>
    </header>

    {@render children()}
</div>

<style>
    .container {
        max-width: 1200px;
        min-height: 100vh;
        margin: 0 auto;

        /* https://grabient.com/LQOgDAnAHANKm3tGIAsZZoy9mL5XwkIPigCYYwUMBGFAVnIDYZbwxr3Pqwg?style=linearSwatches */
        background: linear-gradient(
            90deg,
            #c8d5c8 0%,
            #c8d5c8 2.941%,
            #d0d3bd calc(2.941% + 1px),
            #d0d3bd 5.882%,
            #d4ceaf calc(5.882% + 1px),
            #d4ceaf 8.824%,
            #d5c59e calc(8.824% + 1px),
            #d5c59e 11.765%,
            #d2b88c calc(11.765% + 1px),
            #d2b88c 14.706%,
            #cbaa79 calc(14.706% + 1px),
            #cbaa79 17.647%,
            #c19865 calc(17.647% + 1px),
            #c19865 20.588%,
            #b48651 calc(20.588% + 1px),
            #b48651 23.529%,
            #a5723f calc(23.529% + 1px),
            #a5723f 26.471%,
            #935f2e calc(26.471% + 1px),
            #935f2e 29.412%,
            #804b20 calc(29.412% + 1px),
            #804b20 32.353%,
            #6c3914 calc(32.353% + 1px),
            #6c3914 35.294%,
            #59290b calc(35.294% + 1px),
            #59290b 38.235%,
            #461c06 calc(38.235% + 1px),
            #461c06 41.176%,
            #341105 calc(41.176% + 1px),
            #341105 44.118%,
            #250908 calc(44.118% + 1px),
            #250908 47.059%,
            #18060e calc(47.059% + 1px),
            #18060e 50%,
            #0e0617 calc(50% + 1px),
            #0e0617 52.941%,
            #080924 calc(52.941% + 1px),
            #080924 55.882%,
            #051033 calc(55.882% + 1px),
            #051033 58.824%,
            #061b45 calc(58.824% + 1px),
            #061b45 61.765%,
            #0b2958 calc(61.765% + 1px),
            #0b2958 64.706%,
            #13396b calc(64.706% + 1px),
            #13396b 67.647%,
            #1f4b7f calc(67.647% + 1px),
            #1f4b7f 70.588%,
            #2d5e92 calc(70.588% + 1px),
            #2d5e92 73.529%,
            #3e72a4 calc(73.529% + 1px),
            #3e72a4 76.471%,
            #5085b3 calc(76.471% + 1px),
            #5085b3 79.412%,
            #6498c1 calc(79.412% + 1px),
            #6498c1 82.353%,
            #77a9cb calc(82.353% + 1px),
            #77a9cb 85.294%,
            #8bb8d2 calc(85.294% + 1px),
            #8bb8d2 88.235%,
            #9dc4d5 calc(88.235% + 1px),
            #9dc4d5 91.176%,
            #aecdd4 calc(91.176% + 1px),
            #aecdd4 94.118%,
            #bcd3d0 calc(94.118% + 1px),
            #bcd3d0 97.059%,
            #c7d5c8 calc(97.059% + 1px) 100%
        );
    }

    .top-nav {
        background-color: var(--color-nav-bg);
        padding: 0 1.5rem;
    }

    .top-nav-title {
        display: inline-flex;
        align-items: center;
        gap: 2rem;
        padding: 1.1rem 0;
        color: #f2efe9;
        font-family: "Inter", "Helvetica Neue", Arial, sans-serif;
        font-weight: 700;
        font-size: 1rem;
        letter-spacing: 0.06em;
        text-transform: uppercase;
    }

    .top-nav-subtitle {
        text-transform: none;
        margin-top: 1rem;
        font-weight: 400;
    }

    .top-nav-logo {
        height: 5rem;
        width: auto;
    }
</style>
