<script>
    import { page } from '$app/stores';

    const links = [
        { href: '/about', label: 'about' },
        { href: '/projects', label: 'projects' },
        { href: '/blog', label: 'blog' }
    ];

    $: pathname = $page.url.pathname;
    $: activePath = pathname === '/' ? '/about' : pathname;
</script>

<header class="site-header">
    <a class="brand" href="/about" aria-label="AstroX809 home">
        <img src="/img/Frame.svg" alt="AstroX809" class="brand-logo" />
    </a>
    <div class="top-rule" aria-hidden="true"></div>
    <nav class="site-nav" aria-label="Primary navigation">
        {#each links as link}
            <a class:active={activePath === link.href} class="nav-link" href={link.href}>
                {link.label}
            </a>
        {/each}
    </nav>
</header>
