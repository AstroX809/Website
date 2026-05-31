<script>
    import HeroTitle from '$lib/HeroTitle.svelte';

    const lines = ['astronaut', 'designer', 'material artist'];
</script>

<svelte:head>
    <title>About | AstroX809</title>
    <meta name="description" content="About AstroX809." />
</svelte:head>

<HeroTitle {lines} />
