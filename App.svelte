<script>
  let nGTO1 = 1,
    nGTOETO1 = 1,
    nLTO2 = 1,
    nLTOETO2 = 1,
    nGTO2 = 0,
    nGTOETO2 = 0,
    nLTO1 = 0,
    nLTOETO1 = 0,
    eqO1 = 0,
    eqO2 = 0,
    nEqO1 = 0,
    nEqO2 = 1,
    idO1 = 0,
    idO2 = 0,
    nIdO1 = 0,
    nIdO2 = 1;
  import GT from "./GreaterThan";
  import LT from "./LessThan";
  import GTOET from "./GTOET.svelte";
  import LTOET from "./LTOET.svelte";
  import Equal from "./Equal.svelte";
  import NEq from "./NEqual.svelte";
  import Identity from "./SEqual.svelte";
  import NId from "./SIEqual.svelte";
  import * as stores from "./stores.js";
  function reset() {
    nGTO1 = 1;
    nGTOETO1 = 1;
    nLTO2 = 1;
    nLTOETO2 = 1;
    nGTO2 = 0;
    nGTOETO2 = 0;
    nLTO1 = 0;
    nLTOETO1 = 0;
    eqO1 = 0;
    eqO2 = 0;
    nEqO1 = 0;
    nEqO2 = 1;
    idO1 = 0;
    idO2 = 0;
    nIdO1 = 0;
    nIdO2 = 1;
    stores.resultGT.set(undefined);
    stores.resultLT.set(undefined);
    stores.resultGTOET.set(undefined);
    stores.resultLTOET.set(undefined);
    stores.resultET.set(undefined);
    stores.resultNET.set(undefined);
    stores.resultIT.set(undefined);
    stores.resultNIT.set(undefined);
    stores.eqSOTRG.set(1);
    stores.idSOTRG.set(1);
    stores.nEqSOTRG.set(1);
    stores.nIdSOTRG.set(1);
  }
</script>

<h1>Comparison Operator Playground</h1>
<GT fO={nGTO1} sO={nGTO2} />
<LT fO={nLTO1} sO={nLTO2} />
<GTOET fO={nGTOETO1} sO={nGTOETO2} />
<LTOET fO={nLTOETO1} sO={nLTOETO2} />
<Equal fO={eqO1} sO={eqO2} />
<NEq fO={nEqO1} sO={nEqO2} />
<Identity fO={idO1} sO={idO2} />
<NId fO={nIdO1} sO={nIdO2} />
<button on:click={reset}>Reset</button>