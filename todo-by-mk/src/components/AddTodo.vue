<template>
  <form @submit.prevent="onSubmit()">
    <input type="text" placeholder="Add new execise" @keyup.enter="addItem" v-model="newTodo" />
    <input type="submit" value="send" />
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodo: ""
    };
  },
  methods: {
    addItem() {
      if (this.newTodo.trim()) {
        let newTodoObj = {
          id: Date.now(),
          title: this.newTodo,
          completed: false
        };
        //alert(JSON.stringify(newTodoObj));
        this.$emit("addItem", newTodoObj);
        this.newTodo = "";
      }
    },
    onSubmit() {
      console.log(this, this.$q);
    }
  }
};
</script>