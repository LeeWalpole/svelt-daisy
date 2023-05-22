<script>
	import { onMount } from 'svelte';

	import { Icon } from 'svelte-hero-icons';

	export let text;
	export let link;

	import { page } from '$app/stores';
	let currentRoute = $page.url.pathname;

	// Mapping object to associate the prop value with the corresponding icon component
	const iconMap = {
		Home: Home
		// Add more mappings as needed
	};
</script>

<div class="w-full bg-slate-200">
	<a
		href={link}
		to={link}
		class="w-full bg-slate-100 text-left flex items-center justify-center rounded-full p-3.5
	text-xl desktop:justify-start desktop:gap-3.5 justify-items-start"
	>
		{#if currentRoute === link}
			<Icon src={IconComponent} class="h-7 w-7 text-red-500" solid />
		{:else}
			<Icon src={IconComponent} class="h-7 text-red-500 w-7" outline />{/if}

		<div class="hidden desktop:inline-block desktop:justify-start desktop:items-center">
			{text}
		</div>
	</a>
</div>
