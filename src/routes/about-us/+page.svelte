<script lang="ts">
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	let ready: boolean = false;
	onMount(() => (ready = true));
</script>

<div class="about">
	<div class="container">
		{#if ready}
			<div class="content">
				<h1>About-me</h1>
			</div>
		{/if}
	</div>
</div>

<style>
	.about {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100dvh;
	}
	.about .container {
		display: flex;
		align-items: center;
		color: white;
		margin-top: auto;
		width: 100%;
		height: 100%;}
	.container .content {
		align-items: center;
		margin-left: 20px;
		font-size: 50px;
	}
</style>
