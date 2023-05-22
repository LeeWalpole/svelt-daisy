<script>
	import Swiper from '$lib/components/Swiper.svelte';
	// import Carousel from '$lib/components/Carousel.svelte';
	const images = [
		'https://via.placeholder.com/400x500.png?text=Image+1',
		'https://via.placeholder.com/400x500.png?text=Image+2',
		'https://via.placeholder.com/400x500.png?text=Image+3'
	];

	import { Icon, Heart } from 'svelte-hero-icons';
</script>

<article class="max-w-[360px] bg-slate-900">
	<figure class="w-full aspect-[4/5] bg-red-200 relative">
		<Swiper {images} />
	</figure>
	<section
		class="grid grid-cols-[auto,1fr,auto] px-3.5 gap-3.5 bg-slate-950 rounded-t-[20px] mt-[-20px] overflow-visible z-10 relative"
	>
		<div class="avatar mt-[-25px] z-10">
			<div class="w-28 h-28 rounded-full ring ring-primary ring-offset-base-100 ring-offset-2">
				<img src="https://via.placeholder.com/400x500.png?text=Image+1" />
			</div>
		</div>
		<header class="flex flex-col justify-center items-start">
			<h5 class="text-md">Display Name</h5>
			<p class="text-xs">@username</p>
		</header>
		<header class="flex gap-3.5 justify-end items-center">
			<Icon src={Heart} outline class="h-8 w-8" />
		</header>
	</section>
	<div class="cta-buttons p-3.5 flex justify-between items-center">
		<button class="btn btn-primary">Primary</button>
		<div class="flex gap-3">
			<button class="btn btn-square">1</button>
			<button class="btn btn-square">2</button>
		</div>
	</div>
</article>
