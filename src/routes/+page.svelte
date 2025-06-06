<script lang="ts">
	import Button from '$lib/components/Button.svelte';
	import { Link } from '$lib/index.js';
	import 'opui/src/main.css';
</script>

<h1>svelte-opui</h1>
<p>
    This is a SvelteKit project using the 
    
    <Link href="https://open-props-ui.netlify.app/" target="_blank">OpenPropsUI</Link>
    
    component library.
    It is a simple example of how to use opui components in a SvelteKit application.
</p>
<p>
	Visit

	<Link href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</Link>

	to read the documentation
</p>

<p>
	<Button href="https://svelte.dev/docs/kit" variant="filled" target="_blank">Go to SvelteKit docs</Button>
</p>

<p>
    <Button variant="elevated" size="large" onclick={()=>alert("qwer")}>Button</Button>
</p>