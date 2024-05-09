<script lang="ts">
	import type { SlangWord } from '../../types';
	import SharedSlangLayout from '../SharedSlangLayout.svelte';

	const slangWords = [
		{
			id: 6,
			text: 'Simp',
			definition: 'Someone who does way too much for someone they like',
			example: 'He bought her a car; he’s such a simp.'
		},
		{
			id: 7,
			text: 'No cap',
			definition: 'No lie or seriously',
			example: 'She’s the best singer, no cap.'
		},
		{
			id: 8,
			text: 'Snack',
			definition: 'Someone who looks very attractive',
			example: 'Look at you, a total snack!'
		},
		{
			id: 9,
			text: 'Tea',
			definition: 'Gossip, juicy news',
			example: 'Spill the tea, what did he say?'
		},
		{
			id: 10,
			text: 'Ghost',
			definition: 'To end a relationship by suddenly leaving without explanation',
			example: 'I think I’m going to ghost him, he’s weird.'
		},
		{
			id: 11,
			text: 'Cancel',
			definition: 'To stop supporting someone or something due to unacceptable behavior',
			example: 'She was canceled after those tweets went viral.'
		},
		{
			id: 12,
			text: 'Stan',
			definition: 'An overzealous or obsessive fan, particularly of a celebrity',
			example: 'I stan her so hard, she can do no wrong.'
		},
		{
			id: 13,
			text: 'Clap back',
			definition: 'A comeback filled with attitude',
			example: 'She clapped back so hard, he had nothing to say.'
		},
		{
			id: 14,
			text: 'Extra',
			definition: 'Over the top, excessive',
			example: 'Bringing a sleeping bag to class is a bit extra, don’t you think?'
		},
		{
			id: 15,
			text: 'Glow up',
			definition: 'An incredible transformation',
			example: 'Did you see his glow up? He looks great!'
		},
		{
			id: 16,
			text: 'Hypebeast',
			definition: 'A person who obsesses over acquiring trendy items',
			example: 'He’s a hypebeast when it comes to shoes.'
		},
		{
			id: 17,
			text: 'Lit',
			definition: 'Amazing, exciting',
			example: 'This party is lit!'
		},
		{
			id: 18,
			text: 'Salty',
			definition: 'To be upset, angry, or bitter',
			example: 'Why are you salty? Didn’t you just win?'
		},
		{
			id: 19,
			text: 'Thirsty',
			definition: 'Desperate for attention',
			example: 'Posting ten selfies in one day is a little thirsty.'
		},
		{
			id: 20,
			text: 'Vibe check',
			definition: `An evaluation of a person's emotional state or the atmosphere of a place`,
			example: 'Let’s have a vibe check, how’s everyone doing?'
		},
		{
			id: 21,
			text: 'Woke',
			definition: 'Being aware of social injustices',
			example: 'Stay woke about the issues happening around us.'
		},
		{
			id: 22,
			text: 'Yeet',
			definition: 'To throw something with a lot of force',
			example: 'He just yeeted the ball across the field.'
		},
		{
			id: 23,
			text: 'Lowkey',
			definition: 'To do something discreetly',
			example: 'I lowkey need to start my homework.'
		},
		{
			id: 24,
			text: 'Highkey',
			definition: 'To do something openly or publicly',
			example: 'I highkey love this song.'
		},
		{
			id: 25,
			text: 'Finna',
			definition: 'Going to, intending to',
			example: 'I’m finna get some sleep now.'
		}
	];

	let selectedSlang: SlangWord | null = null;

	function selectSlang(slang: SlangWord) {
		selectedSlang = slang;
	}
</script>

<svelte:head>
	<title>GenZ Slang</title>
</svelte:head>

<SharedSlangLayout
	title="Gen Z Slangs"
	slangs={slangWords}
	{selectSlang}
	{selectedSlang}
	subtitle="Millennials, also known as Generation Y, are the demographic cohort following Generation X and preceding Generation Z."
/>
