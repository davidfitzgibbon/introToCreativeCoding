<script>
	import Slide from '$lib/components/Slide.svelte';
	import InternalSlides from '$lib/components/InternalSlides.svelte';

  let currentSlide = -1;
  let maxSlides = 0;
  let minSlides = -1;
</script>

<Slide>
	<h1>What is Creative Coding?</h1>
  <blockquote class:show={currentSlide >= 0}>
    Any coding undertaken <em>purely for human experience</em>.
  </blockquote>

	<InternalSlides bind:currentSlide {maxSlides} {minSlides} />
</Slide>

<style>
  blockquote {
    opacity: 0;
    transition: opacity 0.5s;
    margin-top: 1em;
  }
  .show {
    opacity: 1;
  }
</style>