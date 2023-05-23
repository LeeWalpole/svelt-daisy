<script>
	// import NavLeft from '$lib/components/NavLeft.svelte';
	import '../app.css';
	import Modals from '$lib/components/Modals.svelte';
	import NavTop from '$lib/components/NavTop.svelte';
	import NavLeft from '$lib/components/NavLeft.svelte';
	import NavBottom from '$lib/components/NavBottom.svelte';
	// import LogoWhite from '$lib/assets/logo-flames-white.webp';
	// import function to register Swiper custom elements
	import { page } from '$app/stores';
	let currentRoute = $page.url.pathname;
</script>

<NavTop />
<div class="app mx-auto flex min-h-screen bg-yellow-50 desktop:max-w-[1240px] text-zinc-300">
	<aside
		class="z-50 nav-left fixed top-0 hidden h-full flex-col items-center space-x-7 tablet:flex tablet:w-[120px] tablet:items-start laptop:w-[120px] desktop:w-[250px] desktop:items-start"
	>
		<NavLeft />
	</aside>
	<div class="ml-0 flex-grow tablet:ml-[120px] desktop:ml-[250px]">
		<main class="relative flex justify-between">
			<slot />
		</main>
	</div>
	<!-- {/* <aside className="widgets hidden laptop:flex laptop:min-w-[300px]">
	Widgets
  </aside> */} -->
</div>
<footer
	class="fixed bottom-0 left-0 flex h-[66px] w-full flex-row items-center bg-yellow-50 tablet:hidden"
>
	<NavBottom />
</footer>

<aside id="modals" style="z-index:999;">
	<Modals {currentRoute} />
</aside>
