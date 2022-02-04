<script>
  import Tile from './Tile.svelte';
  export let guess = "";
  export let states;
</script>

<div class="row">
  <Tile data-tile=0 letter={guess[0] || ""} state={states[0]}/>
  <Tile data-tile=1 letter={guess[1] || ""} state={states[1]}/>
  <Tile data-tile=2 letter={guess[2] || ""} state={states[2]}/>
  <Tile data-tile=3 letter={guess[3] || ""} state={states[3]}/>
  <Tile data-tile=4 letter={guess[4] || ""} state={states[4]}/>
</div>

<style>
  .row {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 5px;
  }
</style>

