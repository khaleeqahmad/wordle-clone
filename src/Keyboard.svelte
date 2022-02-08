<script>
  import Key from './Key.svelte';
  export let states;
</script>

<div class="keyboard">
  <div class="keyboard-row">
    <Key key=q state={states.q} />
    <Key key=w state={states.w} />
    <Key key=e state={states.e} />
    <Key key=r state={states.r} />
    <Key key=t state={states.t} />
    <Key key=y state={states.y} />
    <Key key=u state={states.u} />
    <Key key=i state={states.i} />
    <Key key=o state={states.o} />
    <Key key=p state={states.p} />
  </div>
  <div class="keyboard-row">
    <Key key=a state={states.a} />
    <Key key=s state={states.s} />
    <Key key=d state={states.d} />
    <Key key=f state={states.f} />
    <Key key=g state={states.g} />
    <Key key=h state={states.h} />
    <Key key=j state={states.j} />
    <Key key=k state={states.k} />
    <Key key=l state={states.l} />
  </div>
  <div class="keyboard-row">
    <Key key=Enter name=enter control=true />
    <Key key=z state={states.z} />
    <Key key=x state={states.x} />
    <Key key=c state={states.c} />
    <Key key=v state={states.v} />
    <Key key=b state={states.b} />
    <Key key=n state={states.n} />
    <Key key=m state={states.m} />
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
