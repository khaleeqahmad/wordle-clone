<script>
  import Row from './Row.svelte';

  let guesses = ["", "", "", "", "", ""];
  let currentGuess = 0;

  function isBackspace(key) {
    return key == "Backspace"
  }

  function isEnter(key) {
    return key == "Enter"
  }

  function isAllowedLetter(str) {
    return str.length === 1 && str.match(/[a-z]/i);
    //TODO: Filter out incorrect letters
  }

  function submitGuess() {
    if (guesses[currentGuess].length == 5) {
      //TODO: checkWord();
      currentGuess++
    };
  }

  function deleteLastLetter() {
    guesses[currentGuess] = guesses[currentGuess].slice(0, -1);
  }

  function addLetter(letter) {
    if (isAllowedLetter(letter) && guesses[currentGuess].length < 5) {
      guesses[currentGuess] += letter;
    };
  }

  document.onkeydown = function (event) {
    let key = event.key;

    if (isEnter(key)) {
      submitGuess();
    } else if (isBackspace(key)){
      deleteLastLetter();
    } else {
      addLetter(key);
    };
  }

</script>

<div class="board">
  <Row guess={guesses[0]}/>
  <Row guess={guesses[1]}/>
  <Row guess={guesses[2]}/>
  <Row guess={guesses[3]}/>
  <Row guess={guesses[4]}/>
  <Row guess={guesses[5]}/>
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
</style>
