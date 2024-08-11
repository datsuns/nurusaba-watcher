<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  import Button, { Label } from '@smui/button';

  const dispatch = createEventDispatcher();

	export let online: boolean;
  export let channel: string;
  export let name: string;

  function handleClick() {
    dispatch('customEvent', { message: channel });
  }
</script>

{#if online}
  <Button variant="raised" on:click={handleClick}>
    <Label>{name}</Label>
  </Button>
{:else}
  <Button  color="secondary" variant="raised"  on:click={handleClick}>
    <Label>{name}</Label>
  </Button>
{/if}

<style>
</style>
