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
