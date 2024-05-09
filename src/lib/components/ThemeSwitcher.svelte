<script lang="ts">
	import { onMount } from 'svelte';

	const themes = [
		'default',
		'light',
		'dark',
		'cupcake',
		'bumblebee',
		'emerald',
		'corporate',
		'synthwave',
		'retro',
		'cyberpunk',
		'valentine',
		'halloween',
		'garden',
		'forest',
		'aqua',
		'lofi',
		'pastel',
		'fantasy',
		'wireframe',
		'black',
		'luxury',
		'dracula',
		'cmyk',
		'autumn',
		'business',
		'acid',
		'lemonade',
		'night',
		'coffee',
		'winter',
		'dim',
		'nord',
		'sunset'
	];
	let selectedTheme = 'default';
	let showSidebar = false; // State variable to toggle sidebar

	function selectTheme(theme: string) {
		selectedTheme = theme;
		document.documentElement.setAttribute('data-theme', theme);
		showSidebar = false; // Optionally close the sidebar upon selection
	}

	onMount(() => {
		const currentTheme = document.documentElement.getAttribute('data-theme') ?? '';
		if (themes.includes(currentTheme)) {
			selectedTheme = currentTheme;
		}
	});

	function toggleSidebar() {
		showSidebar = !showSidebar;
	}
</script>

<div class="fixed top-0 right-0 z-50">
	<button class="btn btn-primary m-4" on:click={toggleSidebar}>
		<svg
			class="w-6 h-6"
			fill="none"
			stroke="currentColor"
			viewBox="0 0 24 24"
			xmlns="http://www.w3.org/2000/svg"
		>
			<path
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="2"
				d="M12 1.75c2.137 0 4.16.624 5.872 1.704m-5.872 18.796c-2.137 0-4.16-.624-5.872-1.704m5.872-18.796c-4.97 0-9 3.134-9 7s4.03 7 9 7 9-3.134 9-7-4.03-7-9-7z"
			></path>
		</svg>
	</button>
</div>
<!-- <button class="btn btn-primary fixed top-0 right-0 z-50" on:click={toggleSidebar}
	>Toggle Theme Panel</button
> -->

{#if showSidebar}
	<div
		class="fixed top-0 right-0 w-64 h-full bg-base-100 text-base-content p-5 shadow-lg z-50 overflow-auto"
	>
		<button class="btn btn-ghost btn-circle absolute top-4 right-4" on:click={toggleSidebar}>
			<svg
				class="w-6 h-6"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M6 18L18 6M6 6l12 12"
				></path></svg
			>
		</button>
		<h3 class="text-lg font-bold">Themes</h3>
		<div class="menu p-2 rounded-box">
			{#each themes as theme}
				<button
					class="btn btn-sm btn-block btn-ghost justify-start {selectedTheme === theme
						? 'btn-active'
						: ''}"
					on:click={() => selectTheme(theme)}
				>
					{theme}
				</button>
			{/each}
		</div>
	</div>
{/if}
