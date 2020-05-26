<template>
  <li>
    <span :class="{done: todo.completed}">
      <input type="checkbox" @click="todo.completed = !todo.completed" />
      <strong>{{index+1}}</strong>
      {{todo.title}}
      {{todo.id}}
    </span>
    <button class="rm" @click="deleteTodoItem">&times;</button>
  </li>
</template>
 
<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: {
      type: Number
    }
  },
  methods: {
    deleteTodoItem() {
      return this.$emit("removeTodo", this.index);
    }
  }
};
</script>

<style  scoped>
li {
  border: 3px solid rgb(230, 191, 20);
  display: flex;
  justify-content: space-between;
  margin: 10px;
  padding: 10px;
  padding-left: 5%;
  border-radius: 7%;
  color: rgb(143, 98, 0);
}

.rm {
  border-radius: 40%;
  background-color: rgb(241, 123, 68);
  font-weight: bold;
  border: 2px solid rgb(250, 87, 46);
  color: rgb(255, 255, 255);
}

input {
  margin-right: 10px;
}

.done {
  text-decoration: line-through;
}
</style>
