<script lang="ts">
	import { onMount } from 'svelte';
	import { isChannelLive } from '$lib/TwitchUtils';
	import TwitchChannelEmbed from '$lib/TwitchChannelEmbed/TwitchChannelEmbed.svelte';
  import LayoutGrid, { Cell } from '@smui/layout-grid';
  import Card, { Content, PrimaryAction, Media, MediaContent, } from '@smui/card';

	export let channels: Array<string> = [];

	const liveStatus: Array<boolean> = [];

	onMount(async () => {
		const promises = channels.map(isChannelLive);
		const results = await Promise.allSettled(promises);
		results.forEach((result, i) => {
			if (result.status === 'fulfilled') {
				liveStatus[i] = result.value;
			} else {
				liveStatus[i] = false;
			}
		});
	});
</script>

<LayoutGrid>
  {#each channels as channel, i}
    {#if typeof liveStatus[i] !== 'undefined' && liveStatus[i] === true}
      <Cell>
        <div class="card-container">
          <Card>
            <h2 class="mdc-typography--headline6" style="margin: 0;">
              {channel}
            </h2>
            <div class="embed-entry">
              <TwitchChannelEmbed {channel} id={i.toString()} live={liveStatus[i]} />
            </div>
          </Card>
        </div>
      </Cell>
    {/if}
  {/each}
</LayoutGrid>

<style>
	div {
		display: inline-flex;
		align-items: center;
		margin: 1rem;
	}

  .embed-entry {
    height: 200px;
		margin: 10px;
    background-color: var(--mdc-theme-secondary, #333);
    color: var(--mdc-theme-on-secondary, #fff);
  }
</style>
