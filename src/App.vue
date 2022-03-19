<template>
  <div> 
    <h2>
    Tarea
    <input
      type="text"
      v-model="nuevaTarea"
      placeholder="ingresa nueva tarea"
      @keydown.enter="agregarNuevaTarea"
    />
    <button @click="agregarNuevaTarea">Añade</button>
    <Lista :tareas="tareas" @delete-item="eliminarTarea"></Lista>
    </h2>
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

    eliminarTarea(index) {
      this.tareas.splice(index, 1);
    },
  },
};
</script>


