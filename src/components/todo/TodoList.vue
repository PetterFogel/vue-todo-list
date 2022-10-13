<template>
  <base-card>
    <h1>Todays Todos</h1>
    <hr />
    <h3 v-if="todos <= 0">Please add todays todos!</h3>
    <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
  </base-card>
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
