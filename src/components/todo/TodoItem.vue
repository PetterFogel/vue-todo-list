<template>
  <div>
    <h3>{{ todo.description }}</h3>
    <button @click="deleteTodo(todo.id)">Delete</button>
  </div>
</template>

<script>
export default {
  inject: ["deleteTodo"],
  props: {
    todo: {
      id: {
        type: String,
        required: true,
      },
      description: {
        type: String,
        required: true,
      },
      isPrioritized: {
        type: Boolean,
        required: true,
      },
    },
  },
};
</script>

<style scoped>
div {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
}
</style>
