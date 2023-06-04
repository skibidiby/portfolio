<script lang="ts">
	import { fly } from 'svelte/transition';
	export let url: URL;
</script>

{#key url}
<div
in:fly={ {y: 200, duration: 1500 }}
>
		<slot />
	</div>
{/key}
