<script lang="ts">
  import Button, { Label } from '@smui/button';

	export let online: boolean;
  export let name: string;
</script>

{#if online}
  <Button variant="raised">
    <Label>{name}</Label>
  </Button>
{:else}
  <Button  color="secondary" variant="raised">
    <Label>{name}</Label>
  </Button>
{/if}

<style>
</style>
