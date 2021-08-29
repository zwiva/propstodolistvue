<template>
  <!-- aca se agregan las tareas, es un hijo -->
  <div class="add-tasks">
    <h2>Agrega nueva tarea</h2>
    <div class="add">
      <input type="text" v-model="newTask" placeholder="Ingresa nueva tarea" />
      <button @click="createTask">+</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddTasks",
  data: () => ({
    newTask: "",
  }),
  methods: {
    createTask() {
      // emite evento "new-task" y pasa tarea al metodo que recibe evento
      this.$emit("new-task", this.newTask);
      this.newTask = "";
    },
  },
};
</script>

<style scoped>
h2 {
  color: white;
  text-align: center;
}
.add {
  display: flex;
  width: 100%;
  justify-content: center;
}
input {
  padding: 0.8em;
  border-color: white;
  border-style: none;
}
.add-tasks {
  text-align: center;
  background-color: orange;
  padding: 1em;
}
button {
  background-color: gray;
  padding: 0.8em;
  border-style: none;
  border-color: white;
  color: white;
  font-weight: bolder;
}
</style>