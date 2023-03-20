<script>
	let clicked = false;
</script>

<div>
	<button class="btn btn-primary" on:click={() => (clicked = true)}>
		click here
	</button>
	{#if clicked == true}
		<div>You have clicked the button!</div>
	{:else}
		<div>You have to click the button!</div>
	{/if}
	<!--  -->
</div>
