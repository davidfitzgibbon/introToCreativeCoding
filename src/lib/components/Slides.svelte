<script>
	import Title from '$lib/slides/Title.svelte';
	import Who from '$lib/slides/Who.svelte';
	import Benefits from '$lib/slides/Benefits.svelte';
	import Benefits2 from '$lib/slides/Benefits2.svelte';

	import { current, max } from '$lib/stores/current';

	let slides = [
		Title,
		Who,
		Benefits,
		Benefits2
	];

	max.set(slides.length - 1);

	$current = 2;
	$: currentSlide = slides[$current];
	$: console.log({ $current });
	$: console.log({ $max });
</script>

<svelte:component this={currentSlide} />
