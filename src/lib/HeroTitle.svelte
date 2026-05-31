<script>
    /** @type {string[]} */
    export let lines = [];
</script>

<section class="hero" aria-labelledby="hero-title">
    <h1 id="hero-title">
        {#each lines as line, index}
            {line}{#if index < lines.length - 1}<br />{/if}
        {/each}
    </h1>
</section>

<style>
    .hero {
        position: absolute;
        top: clamp(158px, 19.629vh, 201px);
        left: var(--edge);
        width: min(887px, calc(100vw - (var(--edge) * 2)));
    }

    .hero h1 {
        margin: 0;
        color: var(--ink);
        font-size: clamp(82px, 10.667vw, 128px);
        font-weight: 400;
        line-height: 0.863597640991211;
        letter-spacing: 0;
    }

    @media (max-width: 900px) {
        .hero {
            top: clamp(148px, 20vh, 168px);
        }

        .hero h1 {
            font-size: clamp(74px, 10.6vw, 94px);
        }
    }

    @media (max-width: 760px) {
        .hero {
            top: 168px;
        }

        .hero h1 {
            font-size: clamp(44px, 10.4vw, 74px);
        }
    }
</style>
