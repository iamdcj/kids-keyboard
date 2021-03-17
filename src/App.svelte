<script lang="ts">
  import { alphabet } from "./constants";

  let selection: string = "";

  function handleKeyPress(e) {
    if(selection === e.key) {
      return;
    }
    
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
    <h1
      style="color: {alphabet[selection]?.text
        ? alphabet[selection]?.text
        : '#fff'}"
    >
      {alphabet[selection].label}!
    </h1>
  {/if}
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    color: #fff;
    transition: background-color ease 200ms;
  }

  h1 {
    font-size: 8em;
    font-weight: 600;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
