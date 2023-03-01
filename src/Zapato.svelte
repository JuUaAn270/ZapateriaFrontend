<script>
  export let zapato = {};
</script>

<div class="card">
  <input bind:value={zapato.nombre} class="title" />
  <input
    type="number"
    min="0"
    max="9999.99"
    step=".01"
    bind:value={zapato.precio}
  />
  €
  <slot />
</div>

<style>
  .title {
    font-weight: bold;
  }
  .card {
    background-color: rgb(255, 107, 107);
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    transition: 0.3s;
    padding: 10px;
    margin: 10px;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
  }

  input {
    background-color: inherit;
    padding: 10px;
    font-size: 14px;
    color: black;
    border: 0;
    outline: none;
    margin-left: 5px;
    margin-bottom: 4px;
    max-width: 140px;
    background-color: #fc4a4a;
  }

  input[type="number"] {
    text-align: right;
    width: 100px;
  }
  input:focus {
    background-color: wheat;
  }

  input:required:invalid,
  input:focus:invalid {
    background-color: lightpink;
  }
</style>
