<template>
  <div id="app">
    <h1>Todo application</h1>
    <AddTodo @addItem="addItem" />
    <hr />
    <TodoList :todos="todos" @removeTodo="removeTodo" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
export default {
  name: "App",
  data() {
    return {
      todos: []
    };
  },
  components: {
    TodoList,
    AddTodo
  },
  methods: {
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
    addItem(newTodoObj) {
      this.todos.push(newTodoObj);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
