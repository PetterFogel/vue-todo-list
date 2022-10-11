<template>
  <h3 v-if="todos <= 0">Please add todays todos!</h3>
  <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  inject: ["todos"],
  components: { TodoItem },
};
</script>

<style scoped>
h3 {
  margin: 1rem 0rem;
}
</style>
