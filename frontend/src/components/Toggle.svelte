<script>
	let darkMode = false;
	function toggle() {
        darkMode = !darkMode;
        window.document.body.classList.toggle('dark');
    }
</script>

<button class="ml-2" on:click={toggle}>
	{#if darkMode }
		&#9728;&#65039;	
	{:else}
    	&#127769;		
	{/if}
</button>

<style>
	button {
		background: #212529;
		border: 2px var(--text-color);
		border-radius: 5px;
		color: var(--text-color);
		padding: 5px 10px;
	}
	
	button:active {
		background: inherit;
	}
</style>
