<script lang="ts">
	import type { SvelteHTMLElements } from 'svelte/elements';

	// Based on :where(.link) in opui.css
	let { class: cls, children, ...rest }: SvelteHTMLElements['a'] = $props();
</script>

<a class={['link', cls]} {...rest}>
	{@render children?.()}
</a>
