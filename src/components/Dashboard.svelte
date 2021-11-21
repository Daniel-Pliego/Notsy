<script>
  export let notes;
  import Note from "./Note.svelte";
  import NotePlaceholder from "./NotePlaceholder.svelte";
</script>

<div class="Dashboard">
  <div class="notes-container">
    <NotePlaceholder on:click />
    {#each notes as { id, title, color, text }}
      <Note {id} bind:title {color} bind:text on:update on:color on:delete />
    {/each}
  </div>
</div>

<style>
  .Dashboard {
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
  }
  .notes-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    width: 100%;
    gap: 10px;
  }
</style>
