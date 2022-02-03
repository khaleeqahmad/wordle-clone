<script>
  import Key from './Key.svelte';
  import ControlKey from './ControlKey.svelte';
</script>

<div class="keyboard">
  <div class="keyboard-row">
    <Key character=q />
    <Key character=w />
    <Key character=e />
    <Key character=r />
    <Key character=t />
    <Key character=y />
    <Key character=u />
    <Key character=i />
    <Key character=o />
    <Key character=p />
  </div>
  <div class="keyboard-row">
    <Key character=a />
    <Key character=s />
    <Key character=d />
    <Key character=f />
    <Key character=g />
    <Key character=h />
    <Key character=j />
    <Key character=k />
    <Key character=l />
  </div>
  <div class="keyboard-row">
    <ControlKey name=enter keyCode="13" />
    <Key character=z />
    <Key character=x />
    <Key character=c />
    <Key character=v />
    <Key character=b />
    <Key character=n />
    <Key character=m />
    <ControlKey name=⌫ keyCode="8" />
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
