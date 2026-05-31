<script>
    import '../app.css';
    import SiteFooter from '$lib/SiteFooter.svelte';
    import SiteHeader from '$lib/SiteHeader.svelte';
</script>

<main class="page-shell" aria-label="AstroX809 website">
    <SiteHeader />
    <slot />
    <SiteFooter />
</main>
