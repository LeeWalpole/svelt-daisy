<!-- Modal.svelte -->
<script>
	// import Portal from '$lib/components/ModalPortal.svelte';
	export let modalStyle;
	export let modalTitle;
	export let modalText;
	export let modalLink;
	export let modalID;
	// export let style;
</script>

<!-- Put this part before </body> tag -->

<!-- Put this part before </body> tag -->

{#if modalStyle === 'modal-link'}
	<div class="modal" id={modalID}>
		<a href="#" class="bg-modal" />
		<div class="modal-box">
			<h3 class="text-lg font-bold">{modalTitle}</h3>
			<p class="py-4">
				{@html modalText}
			</p>
			<slot />
			<div class="modal-action">
				<a href="#" class="btn">Close</a>
			</div>
		</div>
	</div>
{:else if modalStyle === 'modal-top'}
	<!-- Render modal-top style -->
	<input type="checkbox" id={modalID} class="modal-toggle" />
	<label for={modalID} class="modal modal-bottom sm:modal-middle cursor-pointer">
		<label class="modal-box relative" for="">
			<h3 class="text-lg font-bold">{modalTitle}</h3>
			<p class="py-4">
				{modalText}
			</p>
			<slot />
			<div class="modal-action">
				<label class="btn" for={modalID}>Yay!</label>
			</div>
		</label>
	</label>
{:else}
	<!-- Render default style or handle unsupported styles -->
	<input type="checkbox" id={modalID} class="modal-toggle" />
	<label for={modalID} class="modal modal-bottom sm:modal-middle cursor-pointer">
		<label class="modal-box relative" for="">
			<h3 class="text-lg font-bold">{modalTitle}</h3>
			<p class="py-4">
				{modalText}
			</p>
			<slot />
			<div class="modal-action">
				<label class="btn" for={modalID}>Yay!</label>
			</div>
		</label>
	</label>
{/if}

<style>
	.bg-modal {
		background: black;
		opacity: 0.75;
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
	}
</style>
