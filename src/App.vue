<template>
  <div>
    <h2>Tareas</h2>
    <input
      type="text"
      v-model="nuevaTarea"
      placeholder="Agregar nueva tarea"
      @keydown.enter="agregarNuevaTarea"
    />
    <button @click="agregarNuevaTarea">Agregar</button>
    <Lista :tareas="tareas" @delete-item="borrarTarea"></Lista>
  </div>
</template>

<script>
import Lista from "./components/Lista";
export default {
  data() {
    return {
      nuevaTarea: "",
      tareas: [],
    };
  },
  components: { Lista },
  methods: {
    agregarNuevaTarea() {
      this.tareas.push(this.nuevaTarea);
      this.nuevaTarea = "";
    },

    borrarTarea(index) {
      this.tareas.splice(index, 1);
    },
  },
};
</script>

<style scoped>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, Helvetica, sans-serif;
    /* font-family: Arial, Helvetica, sans-serif; */
  }
  h2 {
    text-align: center;
  }
  input {
    width: 80%;
    padding: 12px 20px;
    margin: 10px 0 30px 80px;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }

  button {
    background-color: #4CAF50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
    border-radius: 4px;
  }
</style>
