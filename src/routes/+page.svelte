<script lang="ts">
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import Navbar from '../library/navbar.svelte';
	let ready: boolean = false;
	onMount(()=>ready=true)
</script>

<Navbar/>
<div class="home">
<div class="container">
		{#if ready}
		<div class="content" transition:fly={{ y: 200, duration: 2000 }}>
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
		background: rgb(74, 120, 218);
		background: url('noise.png'),
			linear-gradient(
				149deg,
				rgba(74, 120, 218, 1) 29%,
				rgba(0, 212, 255, 1) 72%,
				rgba(51, 185, 80, 1) 100%
			);
		color: white;
		margin-top: auto;
		width: 100%;
		height: 100%;
	}
	.container .content {
		align-items: center;
		margin-left: 20px;
		font-size: 50px;
	}
</style>
