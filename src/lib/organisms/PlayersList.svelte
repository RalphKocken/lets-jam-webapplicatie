<script>
	import PlayerRow from '$lib/molecules/PlayerRow.svelte';

	export let players = [];
	export let reversed = false;
</script>

<table>
	<thead>
		<tr>
			<th>Number</th>
			<th>Name</th>
			<th>Goals</th>
			<th>Assists</th>
			<th>Blocks</th>
			<th>Turnovers</th>
		</tr>
	</thead>
	<tbody>
		{#each players as player}
			<PlayerRow {player} {reversed} />
		{/each}
	</tbody>
</table>

<style>
	table {
		--border-radius: 1em;
		border-radius: var(--border-radius);
		border-collapse: collapse;
		background: white;

		width: 100%;
	}

	thead {
		clip: rect(0 0 0 0);
		position: absolute;
		clip-path: inset(50%);
		width: 1px;
		height: 1px;
		overflow: hidden;
		white-space: nowrap;
	}

	tbody {
		display: flex;
		flex-flow: column nowrap;
		justify-content: space-between;
		height: 100%;
	}
</style>
