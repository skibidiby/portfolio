<script>
	import './global.css';
	import { page } from '$app/stores';
	import Transition from '../components/transition.svelte';
</script>

<nav class="navbar">
	<a href="/about-us">About me</a>
	<a href="/projects">Projects</a>
	<a href="/">
		<div class="logo"><img src="logo.svg" alt="logo" /></div>
	</a>
	<a href="/links">Links</a>
	<a href="/github">Github</a>
</nav>
<Transition url={$page.url}>
	<slot />
</Transition>

<style>
	.navbar {
		display: flex;
		flex-direction: row;
		position: absolute;
		justify-content: space-evenly;
		align-items: center;
		width: 100%;
		color: white;
		font-size: 30px;
		font-weight: bold;
	}
	.navbar a {
		text-decoration: none;
		color: white;
	}
	a:hover {
		text-decoration: underline;
	}
	.navbar .logo img {
		min-height: 80px;
		padding-top: 5px;
	}
</style>
