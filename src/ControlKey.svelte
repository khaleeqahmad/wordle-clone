<script>
  export let name;
  export let keyCode;

  function pressKey (){
    document.dispatchEvent(
      new KeyboardEvent('keydown', {bubbles: true, cancelable: true, keyCode: keyCode})
    )
  }
</script>

<button on:click={pressKey} class="key control">
  {name}
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

  .control {
    color: gray;
    background: #efefef;
    flex: 1.5;
  }
</style>

