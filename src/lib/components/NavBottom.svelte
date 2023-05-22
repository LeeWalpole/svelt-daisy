<script>
	import NavBottomLink from './NavBottomLink.svelte';
</script>

<ul class="flex w-full items-center justify-between">
	<NavBottomLink IconTest="Home" text="home" link="/" />
	<NavBottomLink IconTest="Bell" text="about" link="/about" />
	<NavBottomLink IconTest="Bell" text="profile" link="/profile" />
	<NavBottomLink IconTest="Home" text="about" link="#my-modal-nav-bottom" />
</ul>
