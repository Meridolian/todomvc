<template>
  <div class="todoListContainer">
    <div class="todoForm">
      <label class="todoFormLabel">Add todo</label>
      <input class="todoFormInput" type="text" v-model="todo" />
      <button class="todoFormButton" v-on:click="addTodo(todo)">ADD</button>
    </div>

    <div class="todoList" v-if="todos.length > 0">
      <label class="todoListLabel">Todos</label>

      <div class="todoContainer" v-for="todo in todos" :key="todo.id">
        <input class="todoCheck" type="checkbox" v-model="todo.check" />

        <input class="todoText" type="text" v-model="todo.text" />

        <button class="todoDeleteButton" v-on:click="removeTodo(todo.id)">Delete</button>
      </div>
    </div>
    <div class="noTodos" v-else>
      <label class="todoListLabel">You don't have any todo yet, add it !</label>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props: {},
  data() {
    return {
      todo: "",
      todos: [],
    };
  },
  methods: {
    addTodo: function (todo) {
      this.todos.push({ id: this.todos.length, text: todo, check: false });
    },
    removeTodo: function (index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todoListContainer {
  height: 100%;
  width: 100%;
}

.todoForm {
  height: 25%;
  max-width: 100%;
  margin: 2.5%;
  padding: 1.5%;
  background-color: white;
  border-radius: 10px;
  border: #0f4471 5px solid;
}
.todoFormLabel {
  color: #0f4471;
  font-size: 30px;
  vertical-align: middle;
}
.todoFormInput {
  margin-left: 2.5%;
  vertical-align: middle;
  height: 40px;
  width: 75%;
  border-radius: 10px;
  border: #0f4471 2.5px solid;
  font-size: 25px;
  text-align: center;
  color: #0f4471;
  outline: none !important;
  box-shadow: none !important;
}
.todoFormButton {
  height: 40px;
  width: 7.5%;
  vertical-align: middle;
  margin-left: 5%;
  cursor: pointer;
  color: #0f4471;
  font-size: 20px;
  border-radius: 10px;
  border: #0f4471 2.5px solid;
  outline: none !important;
  box-shadow: none !important;
}
.todoFormButton:hover {
  background-color: #0f4471;
  color: white;
  border: none;
}

.todoList {
  max-width: 100%;
  max-height: 75%;
  margin: 2.5%;
  padding: 1.5%;
}

.todoListLabel {
  color: #0f4471;
  font-size: 30px;
}

.todoContainer {
  height: 50px;
  width: 100%;
  border-top: #0f4471 2px solid;
  margin-top: 1%;
  vertical-align: text-bottom;
}

.todoCheck {
  height: 25px;
  width: 25px;
  border-radius: 10px;
  vertical-align: middle;
  margin: 1%;
}

.todoCheck:checked {
  background-color: red;
}

.todoText {
  margin-left: 0.5%;
  width: 75%;
  border-radius: 10px;
  border: none;
  font-size: 25px;
  vertical-align: middle;
  color: #0f4471;
}
.todoText:hover {
  border: #0f4471 2.5px solid;
}

.todoDeleteButton {
  margin: 0.75%;
  height: 35px;
  width: 7.5%;
  float: right;
  font-size: 20px;
  color: #fc3c3c;
  background-color: white;
  border-radius: 10px;
  border: #fc3c3c 2.5px solid;
  outline: none !important;
  box-shadow: none !important;
  cursor: pointer;
}
.todoDeleteButton:hover {
  background-color: #fc3c3c;
  color: white;
  border: none;
}

.noTodos {
  max-width: 100%;
  margin: 2.5%;
  padding: 1.5%;
}
</style>
