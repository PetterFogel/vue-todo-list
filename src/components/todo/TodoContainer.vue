<template>
  <TodoForm @add-todo="addTodo" />
  <TodoList @open-modal="openModal" />
  <base-modal :open="isModalOpen" @closeModal="closeModal"></base-modal>
</template>

<script>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";
export default {
  components: { TodoForm, TodoList },
  data() {
    return {
      todos: [],
      isModalOpen: false,
    };
  },
  provide() {
    return {
      todos: this.todos,
      deleteTodo: this.deleteTodo,
      openModal: this.openModal,
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
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    },
  },
};
</script>
