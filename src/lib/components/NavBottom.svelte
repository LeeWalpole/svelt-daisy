<script>
	import NavBottomLink from './NavBottomLink.svelte';

	import Modal from '$lib/components/Modal.svelte';
</script>

<ul class="flex w-full items-center justify-between">
	<NavBottomLink IconTest="Home" text="home" link="/" />
	<NavBottomLink IconTest="Bell" text="about" link="/about" />
	<NavBottomLink IconTest="Home" text="about" link="#my-modal-9" />
	<Modal
		modalTitle="Modal Title"
		modalText="This is a single block of text2"
		modalStyle="modal-link"
		modalID="my-modal-9"
		>Next <NavBottomLink IconTest="Home" text="about" link="#my-modal-10" /></Modal
	>

	<Modal modalTitle="Nested!" modalText="Nested" modalStyle="modal-link" modalID="my-modal-10"
		><a href="#my-modal-9">Back</a><NavBottomLink
			IconTest="Home"
			text="about"
			link="#my-modal-10"
		/></Modal
	>
</ul>
