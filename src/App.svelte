<script>
  import Game from './Game.svelte';
</script>


<main>
  <header>
    <h1>Wordle&nbsp;Clone</h1>
    <p>Guess the word</p>
  </header>

  <Game/>
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
    font-size: 2.5em;
    font-weight: bold;
  }

  p {
    text-transform: lowercase;
    font-size: 1.5rem;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
