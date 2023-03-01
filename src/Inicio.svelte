<script>
  import { Link } from "svelte-routing";
</script>

<h1>Zapatería Frontend</h1>
<p>
  <small>
    Backend en
    <a href="https://zapateriabackend.onrender.com">
      https://zapateriabackend.onrender.com
    </a>
  </small>
</p>

<div class="bloque">
  <Link to="/zapatos">
    <div class="resumen">
      <div class="opcion"><h2>Zapatos</h2></div>
      <div class="descripcion">
        <img
          class="Imagen"
          src="/images/SNEAKER-FEVER-JORDAN-QUIZ-2.jpg"
          alt="Imagen"
        />
      </div>
    </div>
  </Link>

  <Link to="/empleados">
    <div class="resumen">
      <div class="opcion"><h2>Empleados</h2></div>
      <div class="descripcion">
        <img
          class="Imagen"
          src="/images/istockphoto-1171159035-170667a.jpg"
          alt="Imagen"
        />
      </div>
    </div>
  </Link>
</div>
<p>
  <small>
    <b>
      Código fuente en
      <a href="https://github.com/JuUaAn270/ZapateriaFrontend">
        https://github.com/JuUaAn270/ZapateriaFrontend
      </a>
    </b>
  </small>
</p>

<style>
  h1,
  div,
  p {
    padding: 3px;
    color: white;
    font-weight: bold;
  }
  a{
    font-weight: bold;
  }
  div {
    padding: 30px;
  }
  .Imagen {
    width: 500px;
    height: 450px;
  }
  .bloque {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }

  .resumen {
    width: 500px;
    height: 500px;
    padding: 5px;
    margin: 0 40px 15px;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.19);
    border: 1px solid #fc4a4a;
    border-radius: 4px;
    background: white;
  }

  .opcion {
    display: flex;
    word-break: break-word;
    padding: 0 10px;
    font-size: 14px;
    font-weight: 700;
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
    font-family: sans-serif;
    color: #333;
    border-radius: 4px;
    background-color: rgb(255, 107, 107);
    min-width: 140px;
    padding: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .descripcion {
    font-size: 14px;
    flex: 1 1 auto;
    word-break: break-word;
    font-family: sans-serif;
    color: #3b4151;
    padding-top: 10px;
    padding-left: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
