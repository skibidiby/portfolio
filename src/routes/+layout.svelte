<script lang="ts">
	import './global.css';
	import { page } from '$app/stores';
	import { base } from "$app/paths";
	import Transition from '../components/transition.svelte';
</script>

<nav class="navbar">
	<a href="{base}/about-us">About me</a>
	<a href="{base}/projects">Projects</a>
	<a href="{base}/">
		<div class="logo"><img src="logo.svg" alt="logo" /></div>
	</a>
	<a href="{base}/contacts">Contacts</a>
	<a href="https://github.com/skibidiby" target="_blank">Github</a>
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
	@media only screen and (max-width: 1200px) {
		.navbar a .logo {
			display: none;
		}
		.navbar a {
			padding-right: 5px;
		}
		.navbar {
			width: max-content;
			overflow-x: scroll;
		}
	}
</style>
