<template>
  <base-card>
    <form @submit.prevent="addTodo(todo)">
      <h2>Add Todo</h2>
      <input type="text" placeholder="Please enter a todo" v-model="todo" />
      <p v-if="isInvalid">Field cannot be empty</p>
      <base-button mode="add-btn">Add Todo</base-button>
    </form>
  </base-card>
</template>

<script>
export default {
  emits: ["add-todo"],
  data() {
    return {
      todo: "",
      isInvalid: false,
    };
  },
  methods: {
    addTodo(newTodo) {
      if (newTodo === "") return (this.isInvalid = true);
      this.$emit("add-todo", newTodo);
      this.isInvalid = false;
      this.todo = "";
    },
  },
};
</script>

<style scoped>
h2 {
  margin-bottom: 1rem;
}
input {
  width: 100%;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border: #fff;
  border-radius: 12px;
  font-size: 1.2rem;
  padding: 0.7rem;
  margin-bottom: 1rem;
}

p {
  color: red;
  margin-bottom: 1rem;
}
</style>
