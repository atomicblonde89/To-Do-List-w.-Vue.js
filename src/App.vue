<template>
  <div id="app" class="text-center">
    <h1 class="py-3">Crear una nueva tarea</h1>
    <label class="pr-4">Tarea</label>
    <input class="me-4 ms-4" type="text" v-model= "duties" placeholder="Ingrese nueva tarea"/>
    <button class="btn btn-dark btn-lg" @click="Agregar">Crear</button>
    <ul>
      <h2>Lista</h2>
      <li v-for="(Tarea, $index) in Tareas" :key="$index">
        {{Tarea}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "app",
  data: () => ({
    duties: "",
    Tareas: ["Compras supermercado", "Botar la basura", "Pagar netflix"]
  }),
  methods:{
    Agregar: function(){
      this.Tareas.push(this.duties)
      this.duties = "";
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
