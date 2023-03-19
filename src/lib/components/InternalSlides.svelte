<script>
	export let currentSlide = 0;
	export let maxSlides = 0;
	export let minSlides = currentSlide;

	const increment = () => (currentSlide = Math.max(currentSlide - 1, minSlides));
	const decrement = () => (currentSlide = Math.min(currentSlide + 1, maxSlides));
</script>

<svelte:body
	on:keydown={(e) =>
		e.key === 'ArrowUp' ? increment() : e.key === 'ArrowDown' ? decrement() : null}
/>
<nav class="arrows">
	<!-- <div class="leftArrow" class:hidden={currentSlide == minSlides}>
		<button on:click={increment}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
				stroke-linecap="round"
				stroke-linejoin="round"
				class="feather feather-arrow-left"
			>
				<line x1="19" y1="12" x2="5" y2="12" />
				<polyline points="12 19 5 12 12 5" />
			</svg>
		</button>
	</div> -->

	<div class="rightArrow" class:hidden={currentSlide == maxSlides}>
		<button on:click={decrement}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
				stroke-linecap="round"
				stroke-linejoin="round"
				class="feather feather-arrow-right"
			>
				<line x1="5" y1="12" x2="19" y2="12" />
				<polyline points="12 5 19 12 12 19" />
			</svg>
		</button>
	</div>
</nav>

<style>
	.arrows {
		position: absolute;
		bottom: 1rem;
		left: 0%;
		width: 100%;
		display: flex;
		justify-content: end;
		padding: 0 1rem;
	}
	.leftArrow,
	.rightArrow {
		display: block;
		justify-content: space-around;
		align-content: space-around;
		color: var(--c-red);
		transition: opacity 0.5s ease;
		rotate: 90deg;
	}
	button {
		background: none;
		cursor: pointer;
		border: none;
		color: var(--c-blue)
	}
	svg {
		width: 2rem;
		height: 2rem;
	}
	.hidden {
		opacity: 0;
	}
	.hidden button {
		cursor: default;
	}
</style>
