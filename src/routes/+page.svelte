<script lang="ts">
	import TwitchChannelGrid from '$lib/TwitchChannelGrid/TwitchChannelGrid.svelte';

	let channels = ['nukadokotaro', 'luluiluu', 'tenshimoko'];
</script>

<TwitchChannelGrid {channels} />
