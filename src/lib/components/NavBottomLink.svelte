<script>
	import { onMount } from 'svelte';

	import { Icon, Home, Bell } from 'svelte-hero-icons';
	export let IconTest;
	export let text;
	export let link;

	import { page } from '$app/stores';
	let currentRoute = $page.url.pathname;

	// Mapping object to associate the prop value with the corresponding icon component
	const iconMap = {
		Home: Home,
		Bell: Bell
		// Add more mappings as needed
	};

	// Get the icon component based on the IconTest prop
	const IconComponent = iconMap[IconTest] || Home; // Default to Home if IconTest is not found in the map

	// Subscribe to page URL changes and update the currentRoute variable
	onMount(() => {
		const unsubscribe = page.subscribe((value) => {
			currentRoute = value.url.pathname.substr(value.url.pathname.lastIndexOf('/'));
		});

		return unsubscribe;
	});
</script>

<li class="flex-auto bg-white">
	<a href={link} to={link}>
		<div
			class="sidebarLink flex items-center justify-center rounded-full p-3.5
text-xl desktop:justify-start desktop:gap-3.5"
		>
			{#if currentRoute === link}
				<Icon src={IconComponent} class="h-7 text-red-500" solid />
			{:else}
				<Icon src={IconComponent} class="h-7 text-red-500" outline />{/if}

			<div class="hidden desktop:inline">
				{text}
			</div>
		</div>
	</a>
</li>
