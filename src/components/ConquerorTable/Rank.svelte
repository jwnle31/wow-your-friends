<script lang="ts">
  import { getOrdinalSuffix } from "../utils";
  import PixelIcon from "../shared/PixelIcon.svelte";

  export let rank: number;

  $: suffix = (rank > 0) ? getOrdinalSuffix(rank) : '';
</script>

{#if rank > 0}
  <div class:berry={rank < 4}>
    {#if rank === 1}
      <PixelIcon src="icons/goldberry.png" alt="Golden berry icon" />
    {:else if rank === 2}
      <PixelIcon src="icons/silverberry.png" alt="Silver berry icon" />
    {:else if rank === 3}
      <PixelIcon src="icons/bronzeberry.png" alt="Bronze berry icon" />
    {/if}
    <span class="rank">{rank}<sup>{suffix}</sup></span>
  </div>
{:else}
  -
{/if}

<style lang="scss">
  div {
    display: grid;
    align-items: center;
    justify-content: center;
    &.berry {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  .rank {
    text-align: center;
  }

  sup {
    font-size: 0.6em;
  }
</style>
