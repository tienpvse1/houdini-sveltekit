<script lang="ts">
	import type { PageData } from './$houdini';

	export let data: PageData;

	$: ({ Launches } = data);
</script>

<button color="alternative" on:click={() => data.Launches.loadNextPage()}>Load more</button>

{#if $Launches.data?.launches}
	{#each $Launches.data?.launches as launch}
		<h1>{launch?.mission_name}</h1>
	{/each}
{/if}
