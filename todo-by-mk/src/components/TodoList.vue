<template>
  <div>
    <ul>
      <Todoitem
        v-for="(todo, index) in todos"
        :todo="todo"
        :key="index"
        :index="index"
        @removeTodo="removeTodo"
      />
    </ul>
  </div>
</template>


<script>
import Todoitem from "@/components/Todoitem";

export default {
  props: {
    todos: {
      type: Array,
      default: []
    }
  },
  components: {
    Todoitem
  },
  methods: {
    removeTodo(index) {
      this.$emit("removeTodo", index);
    }
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>