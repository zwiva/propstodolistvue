<template>
  <!-- es la aplicación y componente padre -->
  <div>
    <!-- @new-task recibe evento y pasa a metodo  addNewTask -->
    <add-tasks @new-task="addNewTask" />
    <!-- :task muestra todas las tareas -->
    <!--  @delete-task recibe evento 'delete-task' que viene del hijo y acciona metodo deleteTask que recibe indice -->
    <list-tasks :tasks="tasks" @delete-task="deleteTask" />
  </div>
</template>

<script>
import AddTasks from "./AddTasks.vue";
import ListTasks from "./ListTasks.vue";

export default {
  name: "TaskApp",
  components: {
    AddTasks,
    ListTasks,
  },
  data: () => ({
    tasks: [],
  }),
  methods: {
    addNewTask(newTask) {
      console.log("para crear y agregar tarea");
      this.tasks.push(newTask);
    },
    deleteTask(index) {
      console.log("para eliminar cada tarea");
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
</style>