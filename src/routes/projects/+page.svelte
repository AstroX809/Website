<script>
    import HeroTitle from '$lib/HeroTitle.svelte';
    import SiteFooter from '$lib/SiteFooter.svelte';
    import SiteHeader from '$lib/SiteHeader.svelte';

    const lines = ['selected', 'projects', 'experiments'];
</script>

<svelte:head>
    <title>Projects | AstroX809</title>
    <meta name="description" content="Projects by AstroX809." />
</svelte:head>

<SiteHeader activePath="/projects" />
<HeroTitle {lines} />
<SiteFooter />
