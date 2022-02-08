<script>
  import Row from './Row.svelte';

  export let word;
  export let currentTurn;
  export let guesses;
  export let turns;
</script>

<div class="board">
  <Row data-row=0 guess={guesses[0]} states={turns[0]}/>
  <Row data-row=1 guess={guesses[1]} states={turns[1]}/>
  <Row data-row=2 guess={guesses[2]} states={turns[2]}/>
  <Row data-row=3 guess={guesses[3]} states={turns[3]}/>
  <Row data-row=4 guess={guesses[4]} states={turns[4]}/>
  <Row data-row=5 guess={guesses[5]} states={turns[5]}/>
</div>

<div class="answer-box">
  {#if currentTurn > 5 }
    <Row guess={word} states={["answer", "answer", "answer", "answer", "answer"]}/>
  {/if}
</div>


<style>
  .board {
    width: 350px;
    height: 420px;
    display: grid;
    margin-left: auto;
    margin-right: auto;
    grid-template-rows: repeat(6, 1fr);
    grid-gap: 5px;
    padding: 10px;
    box-sizing: border-box;
  }

  .answer-box {
    width: 350px;
  }
</style>
