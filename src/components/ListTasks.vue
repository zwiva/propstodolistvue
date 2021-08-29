<template>
  <div class="list-tasks">
    <!-- aca se muestran las tareas, es un hijo-->
    <div class="list">
      <h3>Tareas:</h3>
      <!-- <ul> -->
      <!-- muestra cada tarea -->
      <span v-for="(task, index) in tasks" :key="index" class="d-flex">
        <p>{{ task }}</p>
        <!-- este boton emite evento "delete-task" y le pasa el indice de la tarea a eliminar -->
        <button @click="$emit('delete-task', index)">Eliminar</button>
      </span>
    </div>
    <!-- </ul> -->
  </div>
</template>

<script>
export default {
  name: "ListTasks",
  props: {
    tasks: { type: Array, required: true },
  },
};
</script>

<style scoped>
.list-tasks {
  background-color: gray;
  padding: 1em;
}
.list {
  width: 90%;
  max-width: 500px;
  margin: 0 auto;
}
.d-flex {
  display: flex;
  justify-content: space-between;
  margin-top: 0.5em;
}
span {
  background-color: white;
}
p {
  padding: 0.5em;
  margin: 0.5em;
  color: gray;
}
h3,
button {
  background-color: orange;
  padding: 0.4em;
  border-style: none;
  border-color: white;
  color: white;
  font-weight: bold;
}
</style>
