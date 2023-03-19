<script>
	import Slide from '$lib/components/Slide.svelte';
	import InternalSlides from '$lib/components/InternalSlides.svelte';

  let points = [
		"👔 Doing Product Development, keep it in mind",
		"🎨 For fun and as a hobby",
	];
	let currentSlide = -1;
	let maxSlides = points.length - 1;
	let minSlides = -1;
</script>

<Slide>
	<h1>When should I use it?</h1>
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