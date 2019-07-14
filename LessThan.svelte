<style>
  button {
    padding: 0.25em 0.5em;
    height: 2em;
    font-size: 1em;
  }
  input {
    width: 4em;
    height: 2em;
    padding: 0.25em 0.5em;
    font-size: 1em;
  }
</style>

<script>
  export let fO;
  export let sO;
  import { resultLT } from "./stores";
  function compare() {
    resultLT.set(fO < sO);
  }
  let result;
  resultLT.subscribe(value => (result = value));
</script>

<input bind:value={fO} type=number>
<button on:click={compare}>&#60</button>
<input bind:value={sO} type=number>
<p>Result: {result}</p>