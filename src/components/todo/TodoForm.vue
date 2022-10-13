<template>
  <base-card>
    <form @submit.prevent="addTodo(todo)">
      <h2>Add Todo</h2>
      <input type="text" placeholder="Please enter a todo" v-model="todo" />
      <button>Add Todo</button>
    </form>
  </base-card>
</template>

<script>
export default {
  emits: ["add-todo"],
  data() {
    return {
      todo: "",
    };
  },
  methods: {
    addTodo(newTodo) {
      this.$emit("add-todo", newTodo);
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

button {
  width: 100%;
  font-size: 1.2rem;
  padding: 0.7rem;
  border-radius: 12px;
  color: #fff;
  background: #4caf50;
  border: none;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}
button:hover {
  background: #38813a;
}
</style>
