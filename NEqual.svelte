<!--Inequality playground component-->
<style>
  button {
    padding: 0.25em 0.5em;
    height: 2em;
    font-size: 1em;
  }
  .num {
    width: 4em;
    height: 2em;
    padding: 0.25em 0.5em;
    font-size: 1em;
  }
</style>

<script>
  export let fO;
  export let sO;
  import { resultNET, nEqSOTRG } from "./stores";
  function compare() {
    resultNET.set(fO != sOComputed);
  }
  let result;
  resultNET.subscribe(value => (result = value));
  let sOTRG;
  nEqSOTRG.subscribe(value => (sOTRG = value));
  $: sOComputed = sOTRG == 1 ? parseInt(sO) : `${sO}`;
</script>

<input bind:value={fO} type=number class="num">
<button on:click={compare}>!=</button>
<input bind:value={sO} type=text class="num">
<label>
  <input type="radio" bind:group={$nEqSOTRG} value={1}>
  Number
</label>
<label>
  <input type="radio" bind:group={$nEqSOTRG} value={2}>
  String
</label>
<p>Result: {result}</p>