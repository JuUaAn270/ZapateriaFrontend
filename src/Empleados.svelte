<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Empleado                 from "./Empleado.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let empleado = {};

  onMount(async () => {
    const response = await fetch(URL.empleados);
    const data = await response.json();
    $jsonData = data;
  });

  $: regex = new RegExp(busqueda, "i");
  $: datos = busqueda 
    ? $jsonData.filter(item => regex.test(item.nombre))
    : $jsonData;

</script>

<h1>EMPLEADOS</h1>
<Buscar bind:busqueda />

<div class="container">
  <Empleado bind:empleado>
    <div style="text-align: right">
      <Boton documento={empleado} tipo="insertar" coleccion="empleados" />
    </div>
  </Empleado>
</div>

<div class="container">
  {#each datos as empleado}
    <Empleado {empleado}>
      <div style="text-align: right">
        <Boton documento={empleado} tipo="modificar" coleccion="empleados" />
        <Boton documento={empleado} tipo="eliminar" coleccion="empleados" />
      </div>
    </Empleado>
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