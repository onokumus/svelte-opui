<script lang="ts">
	import type { SvelteHTMLElements } from 'svelte/elements';

	type Variant = 'text' | 'outlined' | 'tonal' | 'filled' | 'elevated';
	type Size = 'small' | 'medium' | 'large';

	interface CustomButtonProps {
		variant?: Variant;
		size?: Size;
		href?: string;
	}

	type ButtonProps = (SvelteHTMLElements['button'] & SvelteHTMLElements['a']) & CustomButtonProps;

	let {
		href,
		variant = 'text',
		size = 'medium', 
		type = 'button',
		class: customClass,
		children,
		disabled,
		...rest
	}: ButtonProps = $props();

	const finalClasses = [
		'button',
		variant !== 'text' && variant,
		size !== 'medium' && size,
		customClass
	];
</script>

{#if href}
	<a
		{href}
		class={finalClasses}
		role="button"
		aria-disabled={!!disabled}
		{...rest}
	>
		{@render children?.()}
	</a>
{:else}
	<button
		{type}
		{disabled}
		class={finalClasses}
		{...rest}
	>
		{@render children?.()}
	</button>
{/if}