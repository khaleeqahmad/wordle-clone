<script>
  import { WORDS, VALID_GUESSES } from './words.js';
  import Board from './Board.svelte';
  import Keyboard from './Keyboard.svelte'

  let word = pickWord();

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
    return WORDS[index];
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

  function isBackspace(key) {
    return key == "Backspace";
  }

  function isEnter(key) {
    return key == "Enter";
  }

  function isLetter(str) {
    return str.length === 1 && str.match(/[a-z]/i);
  }

  function addLetter(letter) {
    if (isLetter(letter) && guesses[currentTurn].length < 5) {
      guesses[currentTurn] += letter;
    };
  }

  function deleteLastLetter() {
    guesses[currentTurn] = guesses[currentTurn].slice(0, -1);
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

  function validGuess(guess) {
    return VALID_GUESSES.includes(guess);
  }

  function evaluate(guess) {
    let states = [];
    let remainingLetters = word;

    for (let i = 0; i < guess.length; i++) {
      let letter = guess[i];

      if (letter == word[i]) {
        states.push("correct");
        remainingLetters = remainingLetters.replace(letter, "");
      } else if (remainingLetters.includes(letter)) {
        states.push("misplaced");
        remainingLetters = remainingLetters.replace(letter, "");
      } else {
        states.push("absent");
      }
    };

    turns[currentTurn] = states;
  }

</script>

<div class="game">
  <Board word={word} guesses={guesses} turns={turns} currentTurn={currentTurn} />
  <Keyboard/>
</div>
