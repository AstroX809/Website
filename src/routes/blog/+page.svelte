<script>
    import HeroTitle from '$lib/HeroTitle.svelte';

    const lines = ['blog', 'notes', 'process'];
</script>

<svelte:head>
    <title>Blog | AstroX809</title>
    <meta name="description" content="Blog posts and notes by AstroX809." />
</svelte:head>

<HeroTitle {lines} />
