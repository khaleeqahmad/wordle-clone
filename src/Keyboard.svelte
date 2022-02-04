<script>
  import Key from './Key.svelte';
</script>

<div class="keyboard">
  <div class="keyboard-row">
    <Key key=q />
    <Key key=w />
    <Key key=e />
    <Key key=r />
    <Key key=t />
    <Key key=y />
    <Key key=u />
    <Key key=i />
    <Key key=o />
    <Key key=p />
  </div>
  <div class="keyboard-row">
    <Key key=a />
    <Key key=s />
    <Key key=d />
    <Key key=f />
    <Key key=g />
    <Key key=h />
    <Key key=j />
    <Key key=k />
    <Key key=l />
  </div>
  <div class="keyboard-row">
    <Key key=Enter name=enter control=true />
    <Key key=z />
    <Key key=x />
    <Key key=c />
    <Key key=v />
    <Key key=b />
    <Key key=n />
    <Key key=m />
    <Key key=Backspace name=⌫ control=true />
  </div>
</div>

<style>
  .keyboard {
    margin: 0 8px;
    user-select: none;
  }

  .keyboard-row {
    display: flex;
    width: 100%;
    margin: 0 auto 8px;
    touch-action: manipulation;
  }
</style>
