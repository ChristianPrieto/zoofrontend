<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Persona                 from "./Persona.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let persona = {};

  onMount(async () => {
    const response = await fetch(URL.personas);
    const data = await response.json();
    $jsonData = data;
  });

  $: regex = new RegExp(busqueda, "i");
  $: datos = busqueda 
    ? $jsonData.filter(item => regex.test(item.nombre))
    : $jsonData;

</script>

<style>
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    flex-wrap: wrap;
  }
</style>

<h1>PERSONAS</h1>
<Buscar bind:busqueda />

<div class="container">
  <Persona bind:persona>
    <div style="text-align: right">
      <Boton documento={persona} tipo="insertar" coleccion="personas" />
    </div>
  </Persona>
</div>

<div class="container">
  {#each datos as persona}
    <Persona {persona}>
      <div style="text-align: right">
        <Boton documento={persona} tipo="modificar" coleccion="personas" />
        <Boton documento={persona} tipo="eliminar" coleccion="personas" />
      </div>
    </Persona>
  {/each}
</div>