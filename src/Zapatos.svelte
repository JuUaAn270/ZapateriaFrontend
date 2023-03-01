<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Zapato                from "./Zapato.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let zapato = {};

  onMount(async () => {
    const response = await fetch(URL.zapatos);
    const data = await response.json();
    $jsonData = data;
  });

  $: datos = $jsonData.filter ( item => RegExp(busqueda, "i").test(item.nombre)) 
  
  // Una forma más complicada de hacer lo anterior
  // $: regex = new RegExp(busqueda, "i");
  // $: datos = busqueda 
  //  ? $jsonData.filter(item => regex.test(item.nombre))
  //  : $jsonData;

</script>

<h1>ZAPATOS</h1>
<Buscar bind:busqueda />

<div class="container">
  <Zapato bind:zapato>
    <div style="text-align: right">
      <Boton documento={zapato} tipo="insertar" coleccion="zapatos" />
    </div>
  </Zapato>
</div>

<div class="container">
  {#each datos as zapato}
    <Zapato {zapato}>
      <div style="text-align: right">
        <Boton documento={zapato} tipo="modificar" coleccion="zapatos" />
        <Boton documento={zapato} tipo="eliminar"  coleccion="zapatos" />
      </div>
    </Zapato>
  {/each}
</div>

<style>
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    flex-wrap: wrap;
  }
</style>
