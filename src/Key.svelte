<script>
  export let key;
  export let control;
  export let name;
  export let state;

  function pressKey (){
    document.dispatchEvent(
      new KeyboardEvent('keydown', {bubbles: true, cancelable: true, key: key})
    )
  }
</script>

<button on:click={pressKey} data-state={state} class="key {control == "true" ? 'control' : undefined}">
  {name || key }
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
    text-transform: uppercase;
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

  .key[data-state=correct] {
    color: white;
    background: #6aaa64;

  }

  .key[data-state=misplaced] {
    color: white;
    background: #c9b458;
  }

  .key[data-state=absent] {
    color: white;
    background: #86888a;
  }

</style>
