<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	export let disabled = false;
	export let ariaLabel = undefined;
	export let fullWidth = false;
	// size / layout props (kept simple so styles match Figma token values)
	export let width = '120px';
	export let height = '32px';
	export let radius = '8px';
	export let label = 'Text';
</script>

<button
	class="btn"
	style="--btn-width: {fullWidth ? '100%' : width}; --btn-height: {height}; --btn-radius: {radius};"
	{disabled}
	aria-label={ariaLabel}
	aria-disabled={disabled}
	{...$$restProps}
	on:pointerdown={(e) => dispatch('pointerdown', e)}
	on:pointerup={(e) => dispatch('pointerup', e)}
	on:mouseenter={(e) => dispatch('mouseenter', e)}
	on:mouseleave={(e) => dispatch('mouseleave', e)}
	on:keydown={(e) => dispatch('keydown', e)}
	on:keyup={(e) => dispatch('keyup', e)}
>
	<span class="label"><slot>{label}</slot></span>
</button>

<style>
	.btn {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		width: var(--btn-width, 120px);
		height: var(--btn-height, 32px);
		padding: 0 12px;
		border-radius: var(--btn-radius, 8px);
		background: #6472bc;
		border: 1px solid rgba(255,255,255,0.25);
		color: rgba(255,255,255,0.85);
		font-family: 'Work Sans', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
		font-weight: 500;
		font-size: 14px;
		line-height: 20px;
		text-align: center;
		white-space: nowrap;
		cursor: pointer;
		user-select: none;
		-webkit-tap-highlight-color: transparent;
		transition: filter 90ms ease, transform 90ms ease, box-shadow 120ms ease;
		box-sizing: border-box;
	}

	.label { display: inline-block; transform: translateY(0); }

	/* Hover state */
	.btn:hover {
		filter: brightness(1.06);
	}

	/* Active / pressed */
	.btn:active {
		filter: brightness(0.98);
	}

	/* Focus-visible (keyboard focus) */
	.btn:focus-visible {
		outline: none;
		box-shadow: 0 0 0 4px rgba(100,114,188,0.18);
	}

	/* Disabled */
	.btn[disabled], .btn[aria-disabled='true'] {
		opacity: 0.48;
		cursor: not-allowed;
		filter: none;
		transform: none;
		box-shadow: none;
	}

	/* Respect full width when requested */
	.btn[style*="100%"] {
		width: 100%;
	}

	/* Small visual polish to vertically center label like Figma */
	.btn .label { margin-top: 0; }
</style>
