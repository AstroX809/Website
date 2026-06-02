<script>
    import HeroTitle from '$lib/HeroTitle.svelte';
    import Button from '$lib/Button.svelte';
    import SiteHeader from '$lib/SiteHeader.svelte';

    const lines = ['astronaut', 'designer', 'material artist'];

    let isHovered = false;
    let isPressed = false;

    function onPointerDown() { isPressed = true; }
    function onPointerUp() { isPressed = false; }
    function onPointerEnter() { isHovered = true; }
    function onPointerLeave() { isHovered = false; isPressed = false; }

    function onKeyDown(e) {
        if (e.key === ' ' || e.key === 'Enter') isPressed = true;
    }
    function onKeyUp(e) {
        if (e.key === ' ' || e.key === 'Enter') isPressed = false;
    }
</script>

<svelte:head>
    <title>About | AstroX809</title>
    <meta name="description" content="About AstroX809." />
</svelte:head>

<Button />
<HeroTitle {lines} />

<div class="button-demo">
    <Button
        on:pointerdown={onPointerDown}
        on:pointerup={onPointerUp}
        on:mouseenter={onPointerEnter}
        on:mouseleave={onPointerLeave}
        on:keydown={onKeyDown}
        on:keyup={onKeyUp}
    >
        {#if isPressed}
            Pressed
        {:else if isHovered}
            Hover
        {:else}
            Text
        {/if}
    </Button>

    <p class="state">State: {isPressed ? 'Pressed' : isHovered ? 'Hover' : 'Rest'}</p>
</div>
