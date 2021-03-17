<script lang="ts">
  import { alphabet } from "./constants";

  let selection: string = "";

  function handleKeyPress(e) {
    selection = e.key;
  }
</script>

<svelte:window on:keydown={handleKeyPress} />
<main
  style="background-color: {alphabet[selection]?.color
    ? alphabet[selection]?.color
    : '#fff'}"
>
  {#if alphabet[selection]?.label}
    <h1>{alphabet[selection].label}!</h1>
  {/if}
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    color: #fff;
    transition: background-color ease 200ms;
  }

  h1 {
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
