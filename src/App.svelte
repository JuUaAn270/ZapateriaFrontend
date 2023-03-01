<script>
  import { setContext } from "svelte";
  import { Router }     from "svelte-routing";
  import Nav            from "./Nav.svelte";
  import Contenido      from "./Contenido.svelte";
  
  const URL = {
    zapatos :  "https://zapateriabackend.onrender.com/api/zapatos/",
    empleados :   "https://zapateriabackend.onrender.com/api/empleados/"
  };

  setContext("URL", URL);
</script>

<Router>
  <Nav />
  <Contenido />
</Router>
<div id="OK">✔️</div>
<div id="KO">❌</div>


<style>

  :global(body) {
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    font-display: swap;     /* Para mejorar rendimiento en carga inicial */
  }

  :global(*) {
    margin: 0;
    padding: 0;
  }

  :global(a:hover) {
    text-decoration: none;
    cursor: pointer;
  }

  :global(div#OK, div#KO) {
    display: none;
    position: fixed;
    top: 60px;
    right: 0px;
    font-size: 60px;
    background-color: transparent;
  }
</style>
