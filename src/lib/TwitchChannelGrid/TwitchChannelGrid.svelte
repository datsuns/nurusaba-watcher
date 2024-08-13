<script lang="ts">
  import { onMount } from 'svelte';
  import { isChannelLive } from '$lib/TwitchUtils';
  import TwitchChannelEmbed from '$lib/TwitchChannelEmbed/TwitchChannelEmbed.svelte';
  import LayoutGrid, { Cell } from '@smui/layout-grid';
  import Card, { Content, PrimaryAction, Media, MediaContent, } from '@smui/card';
  import TwitchChannelStatus from '../TwitchChannelStatus/TwitchChannelStatus.svelte'

  export let channels: Map<string, string> = new Map();

  let channelList: Array<string> = [];
  let channeNamelList: Array<string> = [];
  const liveStatus: Array<boolean> = [];
  let numOfOnline = 0;

  onMount(async () => {
    channeNamelList = [...channels.keys()]
    channelList = [...channels.values()]
    const promises = channelList.map(isChannelLive);
    const results = await Promise.allSettled(promises);
    results.forEach((result, i) => {
      if (result.status === 'fulfilled') {
        liveStatus[i] = result.value;
        if (result.value === true) {
          numOfOnline = ++numOfOnline;
        }
      } else {
        liveStatus[i] = false;
      }
    });
  });

  // 子コンポーネントからのイベントをハンドルする関数
  function handleStatusClicked(event: CustomEvent) {
    const channel = event.detail.message;
    channelList.forEach((result, i) => {
      if ( channel !== channelList[i] ) {
        return;
      }
      if (liveStatus[i] === true ){
        scrollToAnchor(channel);
      }
      else {
        navigateTo(`https://www.twitch.tv/${channel}`);
      }
    });
  }

  function navigateTo(url: string) {
     window.open(url, '_blank');
  }

  function scrollToAnchor(anchorId: string): void {
    const element = document.getElementById(anchorId);
    if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
    }
  }

  function loadChannelId(name: string){
    return channels.get(name) ?? name
  }
</script>

<h1>
  配信中 {numOfOnline} / {channels.size}
</h1>
<LayoutGrid>
  {#each channeNamelList as name, i}
    <Cell span={2}>
      <TwitchChannelStatus channel={loadChannelId(name)} online={liveStatus[i]} name={name} on:customEvent={handleStatusClicked} />
    </Cell>
  {/each}
</LayoutGrid>

<LayoutGrid>
  {#each channeNamelList as name, i}
    {#if liveStatus[i] === true}
      <Cell>
        <div class="card-container" id={loadChannelId(name)}>
          <Card>
            <h2 class="mdc-typography--headline6" style="margin: 0;">
              <a href="https://www.twitch.tv/{loadChannelId(name)}" target="_blank">
                {name}
              </a>
            </h2>
            <div class="embed-entry">
              <TwitchChannelEmbed channel={loadChannelId(name)} id={i.toString()} />
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
    margin: 0px;
    background-color: var(--mdc-theme-secondary, #333);
    color: var(--mdc-theme-on-secondary, #fff);
  }
</style>
