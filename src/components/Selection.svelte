<script lang="ts">
  interface Selection {
    label: string;
    color: string;
    text: string;
  }

  export let selection: Selection;
</script>

<svelte:window on:keydown />
<main style="background-color: {selection?.color}">
  {#if selection?.label}
    <h1 style="color: {selection?.text ? selection?.text : '#fff'}">
      {selection.label}!
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
