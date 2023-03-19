<script>
	import Slide from '$lib/components/Slide.svelte';
	import InternalSlides from '$lib/components/InternalSlides.svelte';

  let benefits = [
		"Can be a genuine solution to issues in work",
    "Increases your understanding of computing",
    "Widens your problem solving horizon",
    "Enhances understanding of design",
    "Actually teaches you maths",
    "Explains nature",
    "It's FUN 🥳",
	];
	let currentSlide = -1;
	let maxSlides = benefits.length - 1;
	let minSlides = -1;
</script>

<Slide>
	<h1>Benefits</h1>
  <ul>
    {#each benefits as benefit, i}
      <li class:show={currentSlide >= i}>👍 {benefit}</li>
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