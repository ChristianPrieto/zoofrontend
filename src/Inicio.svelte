<script>
  import { Link } from "svelte-routing";
</script>

<style>
  h1,
  div,
  p {
    padding: 3px;
  }
  div {
    padding: 30px;
  }

  .bloque {
    display: flex;
    flex-direction: column;
  }
  .resumen {
    display: flex;
    flex-wrap: wrap;    
    padding: 5px;
    margin: 0 0 15px;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.19);
    border: 1px solid rgb(2, 132, 255);
    border-radius: 4px;
  }

  .opcion {
    display: flex;   
    word-break: break-word;
    padding: 0 10px;
    font-size: 14px;
    font-weight: 700;
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
    font-family: sans-serif;
    color: #3b4151;
    border-radius: 4px;
    background: #fdebc9;
    min-width: 140px;
    padding: 10px;
  }

  .descripcion {
    font-size: 14px;
    flex: 1 1 auto;
    word-break: break-word;
    font-family: sans-serif;
    color: #3b4151;
    padding-top: 10px;
    padding-left: 10px;
  }
</style>

<h1>ZooAmaze Frontend</h1>
<p>
  <small>
    <b>Web App made by Christian Prieto</b>
  </small>
</p>


<div class="bloque">
  <Link to="/">
    <div class="resumen">
      <span class="opcion">🛒 Inicio</span>
      <span class="descripcion">Esta página de información.</span>
    </div>
  </Link>

  <Link to="/animales">
    <div class="resumen">
      <span class="opcion">🦓 Animales</span>
      <span class="descripcion">
        Operaciones CRUD de los animales del zoo en una BD.
      </span>
    </div>
  </Link>

  <Link to="/personas">
    <div class="resumen">
      <span class="opcion">👥 Personas</span>
      <span class="descripcion">
        Operaciones CRUD del personal del zoo en una BD.
      </span>
    </div>
  </Link>

</div>
<p>
  <small>
    Backend -->
    <a href="https://animal-zoo.herokuapp.com/">
      https://animal-zoo.herokuapp.com/
    </a>
  </small>
</p>
<p>
  <small>
    <b>
      Código fuente -->
      <a href="https://github.com/ChristianPrieto/zoofrontend">
        https://github.com/ChristianPrieto/zoofrontend
      </a>
    </b>
  </small>
</p>
