<template>
  <section>
    <h1>Todays Todos</h1>
    <hr />
    <TodoList />
  </section>
</template>

<script>
import TodoList from "./TodoList.vue";
export default { components: { TodoList } };
</script>

<style scoped></style>
