<script>
  import { WORDS, VALID_GUESSES } from './words.js';
  import Row from './Row.svelte';

  let word = pickWord();
  // alert(word);
  let currentTurn = 0;
  let guesses = ["", "", "", "", "", ""];

  let turns = {
    0: [ "", "", "", "", "", "" ],
    1: [ "", "", "", "", "", "" ],
    2: [ "", "", "", "", "", "" ],
    3: [ "", "", "", "", "", "" ],
    4: [ "", "", "", "", "", "" ],
    5: [ "", "", "", "", "", "" ]
  }


  function pickWord() {
    let index = Math.floor(Math.random() * WORDS.length);
    // index = 0;

    return WORDS[index];
  }

  function isBackspace(key) {
    return key == "Backspace"
  }

  function isEnter(key) {
    return key == "Enter"
  }

  function isLetter(str) {
    return str.length === 1 && str.match(/[a-z]/i);
  }


  function evaluate(guess) {
    if (guess == word) {
      turns[currentTurn] = ["correct", "correct", "correct", "correct", "correct"];

    } else {
      let states = [];

      for (let i = 0; i < 5; i++) {
        let letter = guess[i];

        if (letter == word[i]) {
          states.push("correct");
        } else if (word.includes(letter)) {
          states.push("misplaced");
        } else {
          states.push("absent");
        }
      };

      turns[currentTurn] = states;
    }
  }

  function validGuess(guess) {
    return VALID_GUESSES.includes(guess);
  }

  function submitGuess() {
    let guess = guesses[currentTurn];
    if (guess.length == 5) {

      if (validGuess(guess)) {
        evaluate(guess);
        currentTurn++
      } else {
        alert("Not a valid guess, try again");
        guesses[currentTurn] = "";
      }
    };
  }


  function deleteLastLetter() {
    guesses[currentTurn] = guesses[currentTurn].slice(0, -1);
  }

  function addLetter(letter) {
    if (isLetter(letter) && guesses[currentTurn].length < 5) {
      guesses[currentTurn] += letter;
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
  <Row id="row-0" data-row=0 guess={guesses[0]} states={turns[0]}/>
  <Row id="row-1" data-row=1 guess={guesses[1]} states={turns[1]}/>
  <Row id="row-2" data-row=2 guess={guesses[2]} states={turns[2]}/>
  <Row id="row-3" data-row=3 guess={guesses[3]} states={turns[3]}/>
  <Row id="row-4" data-row=4 guess={guesses[4]} states={turns[4]}/>
  <Row id="row-5" data-row=5 guess={guesses[5]} states={turns[5]}/>
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
