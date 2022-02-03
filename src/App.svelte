<script>
  import Board from './Board.svelte';
  import Keyboard from './Keyboard.svelte'
</script>


<main>
  <h1>Wordle Clone</h1>
  <p>Guess the word</p>

  <Board/>
  <Keyboard/>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    font-family: 'Clear Sans', 'Helvetica Neue', Arial, sans-serif;
  }

  h1 {
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
