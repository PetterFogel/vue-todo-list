<template>
  <TodoForm @add-todo="addTodo" />
  <TodoList />
</template>

<script>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";
export default {
  components: { TodoForm, TodoList },
  data() {
    return {
      todos: [],
    };
  },
  provide() {
    return {
      todos: this.todos,
      deleteTodo: this.deleteTodo,
    };
  },
  methods: {
    addTodo(description) {
      const newTodo = {
        id: new Date().toISOString(),
        description,
        isDone: false,
      };
      this.todos.unshift(newTodo);
    },
    deleteTodo(todoId) {
      const todoIndex = this.todos.findIndex((todo) => todo.id === todoId);
      this.todos.splice(todoIndex, 1);
    },
  },
};
</script>
