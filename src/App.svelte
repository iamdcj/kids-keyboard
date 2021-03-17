<script lang="ts">
  import Selection from "./components/Selection.svelte";
  import FallBackUI from "./components/FallBackUI.svelte";
  import { alphabet, acceptedKeys } from "./constants";

  let selection: string = "";

  function handleKeyPress(e) {
    if (selection === e.key || !acceptedKeys.includes(e.key)) {
      return;
    }

    selection = e.key;
  }
</script>

<svelte:window on:keydown={handleKeyPress} />

<main>
  {#if alphabet[selection]}
    <Selection selection={alphabet[selection]} />
  {:else}
    <FallBackUI />
  {/if}
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
  }
</style>
