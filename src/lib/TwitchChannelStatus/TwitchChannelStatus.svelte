<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  import Card from '@smui/card';

  const dispatch = createEventDispatcher();

	export let online: boolean;
  export let channel: string;
  export let name: string;

  function handleClick() {
    dispatch('customEvent', { message: channel });
  }
</script>

{#if online}
  <Card style="color: #444444; background-color: #5AFF19; align-items: center; cursor: pointer;" on:click={handleClick}>
    {name}
    <br>
    ({channel})
  </Card>
{:else}
  <Card style="color: #FFFFFF; background-color: #444444; align-items: center; cursor: pointer;" on:click={handleClick}>
    {name}
    <br>
    ({channel})
  </Card>
{/if}

<style>
</style>
