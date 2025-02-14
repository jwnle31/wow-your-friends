<script lang="ts">
  import type { Flag, ProofType } from "./Conqueror";
  import PixelIcon from "../shared/PixelIcon.svelte";

  export let proofType: ProofType;
  export let flags: Flag[];
</script>

<div>
  {#if proofType === 'video'}
    <PixelIcon src="icons/video.png" alt="Video proof" />
  {:else}
    <PixelIcon src="icons/screenshot.png" alt="Screenshot proof" />
  {/if}
  {#if flags.includes('double')}
    <PixelIcon src="icons/moonberry.png" alt="Double golden!" />
  {/if}
  {#if flags.includes('nks')}
    <PixelIcon src="icons/key.png" alt="No key skip!" />
  {/if}
  {#if flags.includes('pre202')}
    <PixelIcon src="icons/ghostberry.png" alt="Pre-202 run!" />
  {/if}
  {#if flags.includes('dts')}
    <PixelIcon src="icons/pink-crystal.png" alt="Dash Trigger skip!" />
  {/if}
  {#if flags.includes('meme')}
    <PixelIcon src="icons/eenox.png" alt="Meme run...why" />
  {/if}
</div>

<style lang="scss">
  div {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    justify-items: center;
    align-items: center;
  }
</style>
