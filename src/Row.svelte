<script>
  import Tile from './Tile.svelte';
  export let word = "";
  export let states;
</script>

<div class="row">
  <Tile data-tile=0 letter={word[0] || ""} state={states[0]}/>
  <Tile data-tile=1 letter={word[1] || ""} state={states[1]}/>
  <Tile data-tile=2 letter={word[2] || ""} state={states[2]}/>
  <Tile data-tile=3 letter={word[3] || ""} state={states[3]}/>
  <Tile data-tile=4 letter={word[4] || ""} state={states[4]}/>
</div>

<style>
  .row {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-gap: 5px;
  }
</style>

