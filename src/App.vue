<template>
  <div>
    <task-app />
  </div>
</template>

<script>
import TaskApp from "./components/TaskApp.vue";

export default {
  name: "App",
  components: {
    TaskApp,
  },
};
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  background-color: gray;
}
</style>
