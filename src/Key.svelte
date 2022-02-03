<script>
  export let character;

  function pressKey (){
    document.dispatchEvent(
      new KeyboardEvent('keydown', {bubbles: true, cancelable: true, key: character, keyCode: character})
    )
  }
</script>

<button on:click={pressKey} class="key">
  {character}
</button>

<style>
  .key {
    font-weight: bold;
    border: 0;
    padding: 0;
    margin: 0 6px 0 0;
    height: 58px;
    border-radius: 4px;
    cursor: pointer;
    user-select: none;
    background-color: #d3d6da;
    color: #1a1a1b;
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    -webkit-tap-highlight-color: rgba(0,0,0,0.3);
  }
</style>

