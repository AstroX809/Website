<script>
    import HeroTitle from '$lib/HeroTitle.svelte';
    import SiteFooter from '$lib/SiteFooter.svelte';
    import SiteHeader from '$lib/SiteHeader.svelte';

    const lines = ['blog', 'notes', 'process'];
</script>

<svelte:head>
    <title>Blog | AstroX809</title>
    <meta name="description" content="Blog posts and notes by AstroX809." />
</svelte:head>

<SiteHeader activePath="/blog" />
<HeroTitle {lines} />
<SiteFooter />
