<script>
	import { fade } from 'svelte/transition';
	import { current, max } from '$lib/stores/current';
</script>

<svelte:body
	on:keyup={(e) => {
		if (e.key === 'ArrowRight') {
			current.set(Math.min($current + 1, $max));
		}
		if (e.key === 'ArrowLeft') {
			current.set(Math.max($current - 1, 0));
		}
	}}
/>

<div class="slide" transition:fade>
	<div class="content">
		<slot />
	</div>
</div>

<style>
	.slide {
		position: absolute;
		display: grid;
		place-items: center;
		height: 100vh;
		max-height: 100vh;
		width: 100%;
		font-size: 2rem;
	}
	.content {
		padding: 1rem;
	}
</style>
