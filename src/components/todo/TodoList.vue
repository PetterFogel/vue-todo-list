<template>
  <base-card>
    <h1>Todays Todos</h1>
    <hr />
    <h3 v-if="todos <= 0">Please add todays todos!</h3>
    <TransitionGroup name="todo-list">
      <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
    </TransitionGroup>
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

.todo-list-enter-from {
  opacity: 0;
  transform: translateX(-30px);
}
.todo-list-enter-active {
  transition: all 800ms ease-out;
}
.todo-list-enter-to {
  opacity: 1;
  transform: translateX(0);
}

.todo-list-leave-from {
  opacity: 1;
}
.todo-list-leave-active {
  transition: all 800ms ease-out;
}
.todo-list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.todo-list-move {
  transition: transform 800ms ease;
}
</style>
