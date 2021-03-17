<script lang="ts">
  import Selection from "./components/Selection.svelte";
  import { alphabet } from "./constants";

  let selection: string = "";

  function handleKeyPress(e) {
    if (selection === e.key) {
      return;
    }

    selection = e.key;
  }
</script>

<Selection on:keydown={handleKeyPress} selection={alphabet[selection]} />
