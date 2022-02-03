<script>
  import Tile from './Tile.svelte';
  export let guess = "";
</script>

<div class="row">
  <Tile letter={guess[0] || ""}/>
  <Tile letter={guess[1] || ""}/>
  <Tile letter={guess[2] || ""}/>
  <Tile letter={guess[3] || ""}/>
  <Tile letter={guess[4] || ""}/>
</div>

<style>
  .row {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 5px;
  }
</style>

