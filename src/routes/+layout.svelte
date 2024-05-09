<script>
	import '../app.css';
	import './styles.css';
	import { themeChange } from 'theme-change';
	import { onMount } from 'svelte';
	import ThemeSwitcher from '$lib/components/ThemeSwitcher.svelte';

	onMount(() => themeChange());
</script>

<ThemeSwitcher />
<slot />
