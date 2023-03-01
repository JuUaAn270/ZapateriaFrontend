<script>
  import { Route }  from "svelte-routing";
  import Inicio     from "./Inicio.svelte";
  import Zapatos  from "./Zapatos.svelte";
  import Empleados   from "./Empleados.svelte";
</script>

<main id="contenido">
  <Route path="/" component={Inicio} />
  <Route path="/zapatos" component={Zapatos} />
  <Route path="/empleados" component={Empleados} />
</main>

<style>
  main {
    padding: 20px;
    padding-top: 50px;
  }
</style>
