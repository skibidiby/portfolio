<script lang="ts">
	export const trailingSlash = 'always';
	import { onMount } from 'svelte';
	let ready: boolean = false;
	onMount(() => (ready = true));
</script>

<div class="home">
	<div class="container">
		{#if ready}
			<div class="content">
				<h1>Hello, I am Victor!</h1>
				<p>I like to code and stuff.</p>
			</div>
		{/if}
	</div>
</div>

<style>
	.home {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100dvh;
	}
	.home .container {
		display: flex;
		align-items: center;
		color: white;
		margin-top: auto;
		width: 100%;
		height: 100%;
	}
	.container .content {
		align-items: center;
		margin-left: 20px;
		font-size: 50px;
		width: 100%;
	}
	/* @media only screen and (max-width: 1200px) {
		.home {
			height: 100dvh;
			width: 100dvw;
		}
	} */
</style>
