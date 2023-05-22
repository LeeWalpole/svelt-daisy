<script>
	import { onMount } from 'svelte';
	import { register } from 'swiper/element/bundle';
	import 'swiper/css';

	register();

	export let images = [];
	let isSwiperReady = false;

	onMount(() => {
		// Simulate loading time
		setTimeout(() => {
			isSwiperReady = true;
		}, 2000);
	});
</script>

{#if isSwiperReady}
	<swiper-container slides-per-view={1} centered-slides={true}>
		{#each images as image}
			<swiper-slide>
				<img src={image} alt="Slide" class="w-full" />
			</swiper-slide>
		{/each}
	</swiper-container>
	<!-- If we need pagination -->
	<div class="swiper-pagination" />
	<!-- If we need navigation buttons -->
	<div class="swiper-button-prev" />
	<div class="swiper-button-next" />
{:else}
	<div class="flex justify-center items-center h-full">
		<p>Loading...</p>
	</div>
{/if}

<style>
</style>
