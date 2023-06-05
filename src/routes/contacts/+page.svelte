<script lang="ts">
	import { onMount } from 'svelte';
	let ready: boolean = false;
	onMount(() => (ready = true));
	let success: boolean;
	interface Data {
		'entry.1941929024': string;
		'entry.2090381845': string;
		'entry.1992853681': string;
	}
	let form_data: Data = {
		'entry.1941929024': '',
		'entry.2090381845': '',
		'entry.1992853681': ''
	};
	function postMessage(data: Data) {
		fetch(
			'https://restful-google-form.vercel.app/api/forms/1FAIpQLSceEmPNOkpFaIN059hMSyE8J37IyPESoxeFDoyWco2j7TZ9HQ',
			{
				method: 'POST',
				body: JSON.stringify(data),
				headers: {
					'Content-type': 'application/json; charset=UTF-8'
				}
			}
		)
			.then((response) => response.json())
			.then((json) => {
				if (json === 200) {
					success = true;
				} else {
					success = false;
				}
			});
	}
</script>

<div class="about">
	<div class="container">
		<h1>Contact me</h1>
		{#if ready}
		<div class="content">
				<form on:submit={() => postMessage(form_data)}>
					<div>
						<label for="name">Name</label>
						<input type="text" id="name" bind:value={form_data['entry.1941929024']} />
					</div>
					<div>
						<label for="email">E-mail</label>
						<input type="text" id="email" bind:value={form_data['entry.2090381845']} />
					</div>
					<div>
						<label for="message">Message</label>
						<textarea id="message" bind:value={form_data['entry.1992853681']} />
					</div>
					<div class="submit">
						<input type="submit" value="Submit" />
					</div>
					<p>
						{success === true
							? 'Thank you for sending me a message!'
							: success === false
							? 'Error'
							: ''}
					</p>
				</form>
			</div>
		{/if}
	</div>
	<!-- <p>{JSON.stringify(form_data)}</p> -->
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
		flex-direction: column;
		color: white;
		width: 100%;
	}
	.about .container h1{
		font-size: 100px;
		padding-left: 20px;
	}
	.container .content {
		display: flex;
		margin-left: 20px;
		font-size: 50px;
		width: 100%;
		justify-content: center;
	}
	.container .content div {
		display: flex;
		flex-direction: row;
		padding-bottom: 5px;
	}
	.container .content div label {
		display: block;
		width: 150px;
	}
	.container .content div input {
		border-radius: 5px;
		height: 50px;
		width: 200px;
		font-size: 20px;
	}
	.container .content div textarea {
		border-radius: 5px;
		min-height: 100px;
		min-width: 400px;
		font-size: 20px;
	}
	.container .content .submit {
		justify-content: flex-end;
	}
	.container .content .submit input{
		cursor: pointer;
	}
	.container .content {
		font-size: 30px;
	}
	@media only screen and (max-width: 1200px) {
		.container .content div {
		display: flex;
		flex-direction: column;
		padding-bottom: 5px;
	}
	}
</style>
