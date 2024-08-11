<script lang="ts">
	import { onMount } from 'svelte';
	import LiveStatus from '../LiveStatus/LiveStatus.svelte';

	export let channel: string;
	export let width = '100%';
	export let height = '100%';
	export let autoplay = true;
	export let muted = true;
	export let parent = 'localhost';
	export let id: string;

	let player: Twitch.Player;


	onMount(async () => {
		player = new Twitch.Player(`twitch-embed-${id}`, {
			channel,
			width,
			height,
			autoplay,
			muted,
			parent
		});
	});
</script>

<div id={`twitch-embed-${id}`} class="twitch-embed">
</div>

<style>
	.twitch-embed {
		aspect-ratio: 16/9;
	}
</style>
