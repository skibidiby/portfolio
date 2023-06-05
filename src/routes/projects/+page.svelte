<script lang="ts">
	import { onMount } from 'svelte';
	interface Project {
		name: string;
		description: string;
		image: string;
		link: string;
	}
	const projects: Project[] = [
		{
			name: 'Amarant',
			description: 'Insurance broker website and mobile application',
			image: 'portfolio/AMARANT.png',
			link: 'https://www.amarantbg.com/'
		},
		{
			name: 'Mira maritime',
			description: 'Website, employement portal and admin panel for a maritime company',
			image: 'portfolio/Mica.png',
			link: 'https://mica-maritime.web.app/'
		},
		{
			name: 'UNIbank',
			description: 'Electronic banking platform of the Macedonian UNIbank',
			image: 'portfolio/UNI_Bank.png',
			link: 'https://www.unibank.mk/ '
		},
		{
			name: 'Apolonia resort',
			description: 'Hotel information site and reservation system',
			image: 'portfolio/APOLONIA_RESORT_HOTEL.png',
			link: 'https://apoloniaresort.com/'
		},
		{
			name: 'NaOpaki',
			description: 'Environmental packaging exchange site',
			image: 'portfolio/NaOpaki.png',
			link: 'https://www.naopaki.bg/'
		},
		{
			name: 'HydroPro',
			description: 'Website and online catalog of a plumbing company',
			image: 'portfolio/HydroPro.png',
			link: 'https://hydropro.bg/'
		},
		{
			name: 'Ucalc',
			description: 'Plaform in beta state to calculate finances for foreign students.',
			image: 'portfolio/ucalc.png',
			link: 'https://ucalc.app/'
		}
	];
	let selected_id: number = 0;
	let ready: boolean = false;
	onMount(() => (ready = true));
</script>

<div class="portfolio">
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
						<a href={projects[selected_id].link} target="_blank">
							<img src={projects[selected_id].image} alt={projects[selected_id].description} />
						</a>
						<a href={projects[selected_id].link} target="_blank">
							<p>🔗 {projects[selected_id].description}</p>
						</a>
					</div>
				</div>
			</div>
		{/if}
	</div>
</div>

<style>
	.portfolio {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100dvh;
	}
	.portfolio .container {
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
		align-items: center;
	}
	.container .content .name {
		display: flex;
		flex-direction: column;
		width: 400px;
	}
	.container .content .description {
		display: flex;
		flex-direction: column;
		width: 100%;
	}
	.container .content .description a {
		text-decoration: none;
		color: white;
	}
	.container .content .description p {
		max-width: 1000px;
	}
	.container .content .description a:hover {
		text-decoration: underline;
	}
	.container .content .description img {
		border: 2px white solid;
		border-radius: 10px;
		max-width: 1000px;
	}
	.container .content .name .active {
		font-weight: bold;
		text-decoration: underline;
	}
	.container .content .name button {
		background: none;
		color: inherit;
		border: none;
		padding: 0;
		font: inherit;
		cursor: pointer;
		outline: inherit;
		padding-bottom: 10px;
	}
	@media only screen and (max-width: 1200px) {
		.portfolio{
			height: 100dvh;
			width: 100dvw;
		}
		.container .content .projects {
			flex-direction: column;
		}
		.container .content .projects {
			flex-direction: column;
		}
		.container .content .description img {
		border: 2px white solid;
		border-radius: 10px;
		max-width: 100%;
	}
	}
</style>
