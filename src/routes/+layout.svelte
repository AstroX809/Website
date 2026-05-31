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

<style>
    .page-shell {
        position: relative;
        width: 100%;
        min-height: 100vh;
        margin: 0 auto;
        overflow: hidden;
    }

    @media (min-width: 1200px) {
        .page-shell {
            min-height: 1024px;
        }
    }

    @media (max-width: 760px) {
        .page-shell {
            min-height: 720px;
        }
    }
</style>
