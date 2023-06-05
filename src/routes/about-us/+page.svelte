<script lang="ts">
	import { onMount } from 'svelte';
	// @ts-ignore
	import { LottiePlayer } from '@lottiefiles/svelte-lottie-player';
	let ready: boolean = false;
	onMount(() => (ready = true));
</script>

<div class="about">
	<div class="container">
		{#if ready}
			<div class="content">
				<h1>A bit about me</h1>
				<p>
					I have no idea how you landed here, but it's nice to meet you! I am a young person with
					a burning passion about technologies and programming. I have professional experience in Web
					development mainly in React.js but in my spare time I love to work on personal projects
					with a wide variety of different tools.
				</p>
			</div>
			<LottiePlayer src="diagram.json" autoplay={true} controlsLayout={undefined} background={undefined} controls={undefined} height={undefined} width={undefined}/>
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
		height: 100%;
	}
	.container .content {
		align-items: center;
		margin-left: 20px;
		font-size: 50px;
	}
	.container .content p {
		font-size: 30px;
		width: 600px;
	}
	@media only screen and (max-width: 1200px) {
		.about {
			height: 100%;
			width: 100%;
		}
		.about .container {
			flex-direction: column;
		}
		.container .content p {
			width: 100%;
		}
	}
</style>
