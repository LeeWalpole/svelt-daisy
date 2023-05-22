<script>
	import NavLeftLink from './NavLeftLink.svelte';
</script>

<div class="mx-auto flex-col justify-center gap-3.5 p-3.5 text-center align-middle tablet:flex">
	<img
		src="https://www.flames.agency/wp-content/uploads/flames-agency-icon-large.png"
		alt=""
		height={44}
		width={44}
		class="mx-auto desktop:mx-0"
	/>

	<NavLeftLink IconTest="Home" text="home" link="/" />
	<NavLeftLink IconTest="Bell" text="Profile " link="/profile" />
	<NavLeftLink IconTest="Home" text="Dashboard " link="/dashboard" />
	<NavLeftLink IconTest="Sparkles" text="Popup" link="#my-modal-2" />

	<label for="my-modal-4" class="btn">open modal</label>
</div>
