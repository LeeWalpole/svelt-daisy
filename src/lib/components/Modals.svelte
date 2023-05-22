<script>
	import Modal from '$lib/components/Modal.svelte';
	export let currentRoute;

	import NavLeftLink from './NavLeftLink.svelte';
</script>

{#if currentRoute === '/profile'}
	<!-- Modals On About Page -->
	<Modal
		modalTitle="Nested Modal"
		modalText="Modal text here"
		modalStyle="modal-link"
		modalID="my-modal-nested"
	/>
{/if}

{#if currentRoute === '/profile'}
	<!-- Modals On Dashboard Page -->
	<Modal
		modalTitle="Modal #1"
		modalText={`Modal text here <a href="#my-modal-nested" class=" btn btn-square">1</a>`}
		modalStyle="modal-link"
		modalID="my-modal-1"
	/>
{/if}

<!-- Generic Modals -->
<Modal
	modalTitle="Modal Title"
	modalText="This is a single block of text"
	modalStyle="modal-link"
	modalID="my-modal-2"
/>

<Modal
	modalTitle="Modal Title"
	modalText="This is a single block of text"
	modalStyle="modal-bottom"
	modalID="my-modal-4"
/>

<Modal
	modalTitle="Nav Bottom"
	modalText="Modal text here"
	modalStyle="modal-link"
	modalID="my-modal-nav-bottom"
/>

<!-- Put this part before </body> tag -->
<div class="modal" id="modal-sideNav">
	<div class="modal-box">
		<NavLeftLink IconTest="Home" text="home" link="/" />
		<NavLeftLink IconTest="Bell" text="Profile " link="/profile" />
		<NavLeftLink IconTest="Home" text="Dashboard " link="/dashboard" />
		<NavLeftLink IconTest="Sparkles" text="Popup" link="#my-modal-2" />
		<div class="modal-action">
			<a href="#" class="btn">Yay!</a>
		</div>
	</div>
</div>
