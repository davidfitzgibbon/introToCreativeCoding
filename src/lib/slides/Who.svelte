<script>
	import Slide from '$lib/components/Slide.svelte';
	import InternalSlides from '$lib/components/InternalSlides.svelte';

let points = [
	"👶 Dublin",
	"🏎 Wheels",
	"🎸 Noise",
	"💰 Indo",
	"🥳 Creative Coding - Lofi",
];
let currentSlide = -1;
let maxSlides = points.length - 1;
let minSlides = -1;
</script>

<Slide>
	<h1>Who am I?</h1>

	<ul>
		{#each points as point, i}
      <li class:show={currentSlide >= i}>{point}</li>
    {/each}
	</ul>
	<InternalSlides bind:currentSlide {maxSlides} {minSlides} />

</Slide>

<style>
  li {
    opacity: 0;
    transition: opacity 0.5s;
  }
  .show {
    opacity: 1;
  }
</style>