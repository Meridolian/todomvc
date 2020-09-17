<template>
  <div id="app">
    <Navbar />
    <TodoList msg="ui" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    Navbar,
    TodoList,
  },
};
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  margin: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
}
</style>
