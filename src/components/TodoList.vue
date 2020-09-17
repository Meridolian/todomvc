<template>
  <div class="todoListContainer">
    <div class="todoForm">
      <label class="todoFormLabel">Add todo</label>
      <input class="todoFormInput " type="text" v-model="todo" />
      <button class="todoFormButton" v-on:click="addTodo(todo)">ADD</button>
    </div>

    <div class="todoList">
      <label class="todoListLabel">Todos</label>

      <div class="todoContainer">
        
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Vuex from "vuex";

Vue.use(Vuex);

const store = new Vuex.Store({
  state: {
    todos: [],
  },
  mutations: {
    addTodo(state, todo) {
      state.todos.push(todo);
    },
    removeTodo(state, todoId) {
      state.todos.splice(todoId, 1);
    },
  },
});

export default {
  name: "TodoList",
  props: {},
  store: store,
  data() {
    return {
      id: 0,
      todo: "",
    };
  },
  methods: {
    addTodo: function(todo){
      this.addTodo(this.state, todo);
    },
    removeTodo: function(todoId) {
      this.removeTodo(this.state, todoId);
    }
  }
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
  background-color: rgba(0, 0, 0, 0.75);
  border-radius: 10px;
}
.todoFormLabel {
  color: white;
  font-size: 30px;
  vertical-align: middle;
}
.todoFormInput {
  margin-left: 2.5%;
  vertical-align: middle;
  height: 40px;
  width: 75%;
  border-radius: 10px;
  font-size: 25px;
  text-align: center;
  color: rgba(0, 0, 0, 0.75);
  border: none;
  outline: none !important;
  box-shadow: none !important;
}
.todoFormButton {
  height: 40px;
  width: 7.5%;
  vertical-align: middle;
  margin-left: 5%;
  cursor: pointer;
  color: rgba(0, 0, 0, 0.75);
  font-size: 20px;
  border-radius: 10px;
  border: none;
  outline: none !important;
  box-shadow: none !important;
}
.todoFormButton:hover {
  background-color: transparent;
  color: white;
  border: white 2.5px solid;
}


.todoList {

}
.todoListLabel {

}
.todoContainer {

}
.todoLabel {

}
.todoModifyButton {

}
.todoDeleteButton {

}
</style>
