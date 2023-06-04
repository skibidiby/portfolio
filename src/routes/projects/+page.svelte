<script lang="ts">
	import { onMount } from 'svelte';
	interface Project {
		name: string;
		description: string;
		image: string;
	}
	const projects: Project[] = [
		{ name: 'Amarant', description: 'woqeiqwpoesal;dka', image: 'image' },
		{ name: 'Mira', description: 'dadadad;dka', image: 'image' }
	];
	let selected_id: number = 0;
	let ready: boolean = false;
	onMount(() => (ready = true));
</script>

<div class="about">
	<div class="container">
		{#if ready}
			<div class="content">
				<div class="projects">
					<div class="name">
						{#each projects as project, i (i)}
							<button on:click={() => (selected_id = i)} class={selected_id === i ? 'active' : ''}
								>{project.name}</button
							>
						{/each}
					</div>
					<div class="description">
						{projects[selected_id].description}
					</div>
				</div>
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
		height: 100%;
	}
	.container .content {
		align-items: center;
		margin-left: 20px;
		font-size: 50px;
	}
	.container .content {
		font-size: 30px;
	}
	.container .content .projects {
		display: flex;
		flex-direction: row;
		width: 100%;
	}
	.container .content .name {
		display: flex;
		flex-direction: column;
		width: 400px;
	}
	.container .content .name .active {
		font-weight: bold;
	}
	.container .content .name button {
		background: none;
		color: inherit;
		border: none;
		padding: 0;
		font: inherit;
		cursor: pointer;
		outline: inherit;
	}
</style>
