<template>
  <TheHeader />
  <TodoForm @add-todo="addTodo" />
  <TodoContainer />
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
import TodoContainer from "./components/todo/TodoContainer.vue";
import TodoForm from "./components/todo/TodoForm.vue";
export default {
  components: { TheHeader, TodoContainer, TodoForm },
  data() {
    return {
      todos: [],
    };
  },
  provide() {
    return {
      todos: this.todos,
    };
  },
  methods: {
    addTodo(description) {
      const newTodo = {
        id: new Date().toISOString(),
        description,
        isPrioritized: false,
      };
      this.todos.unshift(newTodo);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

section {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
}
</style>
