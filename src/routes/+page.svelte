<script lang="ts">
	import { goto } from '$app/navigation';
	import { onMount, onDestroy } from 'svelte';
	import { slide } from 'svelte/transition';
	import { base } from '$app/paths';
	let slangWords = [
		{ word: 'Lit', meaning: 'Amazing, exciting' },
		{ word: 'Salty', meaning: 'Bitter, upset' },
		{ word: 'Ghosting', meaning: 'Ignoring someone deliberately' },
		{ word: 'Yeet', meaning: 'To throw something with vigor' },
		{ word: 'Low key', meaning: 'Subtly or secretly' }
	];
	let index = 0;
	let roller: number;

	onMount(() => {
		roller = setInterval(() => {
			if (index === slangWords.length - 1) index = 0;
			else index++;
		}, 3500);
	});

	onDestroy(() => {
		clearInterval(roller);
	});
</script>

<svelte:head>
	<title>GenSlang</title>
</svelte:head>

<div class="flex flex-col h-screen justify-center items-center bg-base-200">
	<div class="text-center max-w-md">
		<h1 class="text-5xl font-bold">Welcome to GenSlang!</h1>
		<p class="py-6">Dive into the dynamic world of generational slang.</p>

		<div class="mb-8">
			{#key index}
				<p transition:slide class="text-3xl font-semibold mb-4">
					<span>{slangWords[index].word}</span> - {slangWords[index].meaning}
				</p>
			{/key}
		</div>

		<div class="card shadow-xl">
			<div class="card-body">
				<h2 class="card-title">What is Slang?</h2>
				<p>
					Slang consists of informal words or phrases that are often playful, vivid, and reflect the
					dynamics of social identity and group membership.
				</p>
			</div>
		</div>

		<div class="flex flex-wrap justify-center gap-4 mt-8">
			<button class="btn btn-primary btn-wide btn-lg" on:click={() => goto(`${base}/millennials`)}>
				<i class="fas fa-grin-stars mr-2"></i> Millennial Slang
			</button>
			<button class="btn btn-primary btn-wide btn-lg" on:click={() => goto(`${base}/genz`)}>
				<i class="fas fa-rocket mr-2"></i> Gen Z Slang
			</button>
		</div>
	</div>
</div>

<style>
	.btn-lg {
		width: 300px;
		padding: 1.5rem 2rem;
	}
</style>
