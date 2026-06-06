<script>
    import HeroTitle from '$lib/HeroTitle.svelte';
    import SiteFooter from '$lib/SiteFooter.svelte';
    import SiteHeader from '$lib/SiteHeader.svelte';

    const lines = ['astronaut', 'designer', 'material artist'];
</script>

<svelte:head>
    <title>AstroX809</title>
    <meta name="description" content="AstroX809 portfolio home page." />
</svelte:head>

<SiteHeader activePath="/" />
<HeroTitle {lines} />
<SiteFooter />
