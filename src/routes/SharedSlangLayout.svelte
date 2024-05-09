<script>
	export let title;
	export let subtitle;
	export let slangs;
	export let selectSlang;
	export let selectedSlang;

	import { goto } from '$app/navigation';
	function goBackToHome() {
		goto('/', { replaceState: true });
	}
</script>

<div class="flex flex-col h-screen justify-center items-center bg-base-200">
	<div class="container p-4">
		<button class="btn btn-outline mb-4" on:click={goBackToHome}>Back to Home</button>
		<h1 class="text-5xl font-bold text-center mb-4">{title}</h1>
		<p class="text-xl text-center py-3">
			{subtitle}
		</p>

		<div class="flex flex-row justify-evenly items-start gap-6 w-full py-6">
			<div class="w-1/3 rounded-box p-4 shadow-lg" style="height: 60vh; overflow-y: auto;">
				<ul class="menu-list text-xl">
					{#each slangs as slang}
						<li
							class={`px-4 py-3 rounded-lg transition-colors cursor-pointer ${selectedSlang === slang ? 'bg-primary text-primary-content' : 'hover:bg-primary'}`}
							on:click={() => selectSlang(slang)}
						>
							{slang.text}
						</li>
					{/each}
				</ul>
			</div>
			<div class="w-2/3 rounded-box p-6 shadow-lg">
				{#if selectedSlang}
					<h2 class="text-4xl font-bold mb-2">{selectedSlang.text}</h2>
					<p class="text-lg mb-4">{selectedSlang.definition}</p>
					<p class="text-lg font-semibold mb-1">Example:</p>
					<p class="text-lg italic">{selectedSlang.example}</p>
				{:else}
					<p class="text-xl italic text-center">Please select a slang term to view details.</p>
				{/if}
			</div>
		</div>
	</div>
</div>
