<script>
	import Title from '$lib/slides/Title.svelte';
	import Who from '$lib/slides/Who.svelte';
	import Benefits from '$lib/slides/Benefits.svelte';
	import Whatisit from '$lib/slides/Whatisit.svelte';
	import When from '$lib/slides/When.svelte';
	import Whatisit2 from '$lib/slides/Whatisit2.svelte';
	import Origin from '$lib/slides/Origin.svelte';
	import CSS from '$lib/slides/CSS.svelte';
	import SVG from '$lib/slides/SVG.svelte';
	import Canvas from '$lib/slides/Canvas.svelte';
	import CSS2 from '$lib/slides/CSS2.svelte';
	import SVG2 from '$lib/slides/SVG2.svelte';
	import Cadbury from '$lib/slides/Cadbury.svelte';
	import Demo from '$lib/slides/Demo.svelte';
	import Links from '$lib/slides/Links.svelte';
	import Thanks from '$lib/slides/Thanks.svelte';

	import { current, max } from '$lib/stores/current';

	let slides = [
		Title,
		Who,
		Benefits,
		Whatisit,
		When,
		Whatisit2,
		Origin,
		CSS,
		SVG,
		Canvas,
		CSS2,
		SVG2,
		Cadbury,
		Demo,
		Links,
		Thanks,
	];

	max.set(slides.length - 1);

	$current = 0;
	$: currentSlide = slides[$current];
	$: console.log({ $current });
	$: console.log({ $max });
</script>

<svelte:component this={currentSlide} />
