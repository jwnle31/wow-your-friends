<script lang="ts">
  import { getOrdinalSuffix } from "../utils";
  import PixelIcon from "../shared/PixelIcon.svelte";

  export let rank: number;

  $: suffix = (rank > 0) ? getOrdinalSuffix(rank) : '';
</script>

{#if rank > 0}
  <div class={rank >= 4 ? 'padded' : ''}>
    {#if rank === 1}
      <PixelIcon src="icons/goldberry.png" alt="Golden berry icon" />
    {:else if rank === 2}
      <PixelIcon src="icons/silverberry.png" alt="Silver berry icon" />
    {:else if rank === 3}
      <PixelIcon src="icons/bronzeberry.png" alt="Bronze berry icon" />
    {/if}
    <span>{rank}<sup>{suffix}</sup></span>
  </div>
{:else}
  -
{/if}

<style>
  div {
    display: flex;
    justify-content: left;
    align-items: center;
    gap: 0.4em;
  }

  .padded {
    padding-left: 1.6em;
  }

  sup {
    font-size: 0.8em;
    vertical-align: super;
  }
</style>
