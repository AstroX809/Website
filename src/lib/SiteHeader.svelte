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

<style>
    .site-header {
        position: absolute;
        top: clamp(54px, 8.301vh, 85px);
        left: 50%;
        width: var(--content-width);
        height: 56px;
        transform: translateX(-50%);
    }

    .brand,
    .brand-logo,
    .site-nav,
    .nav-link {
        display: flex;
    }

    .brand {
        position: absolute;
        top: 0;
        left: 0;
        width: clamp(244px, 26.734vw, 320.804px);
        height: clamp(43.7px, 4.667vw, 55.999px);
        align-items: center;
    }

    .brand-logo {
        width: 100%;
        height: 100%;
    }

    .top-rule {
        position: absolute;
        top: clamp(21.58px, 2.307vw, 27.68px);
        right: clamp(254px, 24.142vw, 289.7px);
        left: clamp(262px, 28.358vw, 340.3px);
        height: 1px;
        background: var(--ink);
    }

    .site-nav {
        position: absolute;
        top: clamp(6px, 0.667vw, 8px);
        right: 0.2px;
        width: clamp(245px, 22.5vw, 270px);
        gap: clamp(10px, 1.25vw, 15px);
        align-items: flex-start;
        color: var(--ink);
        font-size: clamp(14px, 1.333vw, 16px);
        font-weight: 600;
        line-height: normal;
    }

    .nav-link {
        height: clamp(36px, 3.333vw, 40px);
        align-items: center;
        justify-content: center;
        border-radius: 9px;
    }

    .nav-link:nth-child(1),
    .nav-link:nth-child(3) {
        width: clamp(66px, 6.333vw, 76px);
    }

    .nav-link:nth-child(2) {
        width: clamp(78px, 7.333vw, 88px);
    }

    .nav-link.active {
        background: var(--button);
        color: var(--bg);
    }

    @media (max-width: 900px) {
        .site-header {
            top: 48px;
        }

        .top-rule {
            right: clamp(230px, 29.8vw, 254px);
            left: clamp(232px, 30.2vw, 262px);
        }
    }

    @media (max-width: 760px) {
        .site-header {
            top: 32px;
            height: 104px;
        }

        .brand {
            width: 244px;
            height: 43.7px;
        }

        .top-rule {
            top: 60px;
            right: 0;
            left: 0;
        }

        .site-nav {
            top: 78px;
            right: auto;
            left: 0;
        }
    }
</style>
