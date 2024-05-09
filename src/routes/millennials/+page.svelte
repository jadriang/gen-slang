<script lang="ts">
	import type { SlangWord } from '../../types';
	import SharedSlangLayout from '../SharedSlangLayout.svelte';

	const slangWords = [
		{
			id: 1,
			text: 'Bae',
			definition: "Endearment for one's partner, short for 'before anyone else'",
			example: "Can't wait to spend the weekend with bae."
		},
		{
			id: 2,
			text: 'On fleek',
			definition: 'Perfectly executed, stylish',
			example: 'Your eyebrows are on fleek today!'
		},
		{
			id: 3,
			text: 'YOLO',
			definition:
				'You Only Live Once; used to express the idea that one should enjoy life, even if that entails taking risks',
			example: 'Just booked a last-minute vacation to Spain, YOLO!'
		},
		{
			id: 4,
			text: 'FOMO',
			definition:
				'Fear of Missing Out; anxiety that an exciting event may currently be happening elsewhere',
			example: 'I have major FOMO from skipping that party last night.'
		},
		{
			id: 5,
			text: 'It’s lit',
			definition: 'Exciting or excellent',
			example: 'This concert is lit!'
		},
		{
			id: 6,
			text: 'Throw shade',
			definition: 'To give someone a dirty look or speak disrespectfully about them',
			example: 'Why did she have to throw shade in the meeting like that?'
		},
		{
			id: 7,
			text: 'Squad goals',
			definition: 'Aspirations that a group of friends or a team would like to achieve',
			example: `Them always having each other's backs are total squad goals.`
		},
		{
			id: 8,
			text: 'Netflix and chill',
			definition:
				'A euphemism for spending time together at home and possibly engaging in sexual activity, with Netflix in the background',
			example: 'He invited me over to Netflix and chill.'
		},
		{
			id: 9,
			text: 'Basic',
			definition: 'Lacking originality, being overly mainstream or not original',
			example: 'She’s so basic, always wearing what everyone else is.'
		},
		{
			id: 10,
			text: 'Adulting',
			definition: 'Acting in a manner of a responsible adult',
			example: 'I spent the whole day cleaning and paying bills, just adulting.'
		},
		{
			id: 11,
			text: 'TBH',
			definition: 'To Be Honest',
			example: 'TBH, I wasn’t even surprised they broke up.'
		},
		{
			id: 12,
			text: 'Turnt',
			definition: 'Excited or energized, often in a party context',
			example: 'Everyone was turnt at Dave’s wedding reception.'
		},
		{
			id: 13,
			text: 'Feels',
			definition: 'A wave of emotions that cannot be adequately explained',
			example: 'That movie gave me all the feels.'
		},
		{
			id: 14,
			text: 'SMH',
			definition: 'Shaking My Head; expression of disapproval or disbelief',
			example: 'She was late again today, smh.'
		},
		{
			id: 15,
			text: 'Can’t even',
			definition: 'Used to express a feeling of being overwhelmed or unable to cope',
			example: 'He’s so cute, I can’t even!'
		},
		{
			id: 16,
			text: 'Hangry',
			definition: 'Bad-tempered or irritable as a result of hunger',
			example: 'I need to eat soon, I’m starting to get hangry.'
		},
		{
			id: 17,
			text: 'Obvi',
			definition: 'Obviously',
			example: 'Obvi we’re going to the concert, why wouldn’t we?'
		},
		{
			id: 18,
			text: 'Jelly',
			definition: 'Jealous',
			example: 'I’m so jelly of her new car!'
		},
		{
			id: 19,
			text: 'Totes',
			definition: 'Totally',
			example: 'I totes agree with you.'
		},
		{
			id: 20,
			text: 'Vibe',
			definition: `A person's emotional state or the atmosphere of a place as communicated to and felt by others`,
			example: 'The vibe in this restaurant is really chill.'
		}
	];

	let selectedSlang: SlangWord | null = null;

	function selectSlang(slang: SlangWord) {
		selectedSlang = slang;
	}
</script>

<svelte:head>
	<title>Millennials Slang</title>
</svelte:head>

<SharedSlangLayout
	title="Millennial Slangs"
	slangs={slangWords}
	{selectSlang}
	{selectedSlang}
	subtitle="A look into popular slang terms used by Millennials that often reflect group identity and
social dynamics."
/>
