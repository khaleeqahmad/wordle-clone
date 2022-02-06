<script>
  export let letter = "";
  export let state = "";
</script>

<div class="tile" data-state={state} >
  {letter}
</div>

<style>
  .tile {
    width: 100%;
    align-items: center;
    padding: 0.5rem 0;
    text-align: center;
    font-size: 2rem;
    line-height: 2rem;
    font-weight: bold;
    vertical-align: middle;
    box-sizing: border-box;
    color: black;
    text-transform: uppercase;
    user-select: none;
    border: 1px solid #d3d6da;
  }

  .tile[data-state=answer] {
    color: black;
    border: 1px solid black;
    background: #6aaa64;
  }

  .tile[data-state=correct] {
    color: white;
    background: #6aaa64;
  }

  .tile[data-state=misplaced] {
    color: white;
    background: #c9b458;
  }

  .tile[data-state=absent] {
    color: white;
    background: #86888a;
  }

</style>
