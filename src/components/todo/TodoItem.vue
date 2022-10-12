<template>
  <section>
    <div>
      <h4>{{ todo.description }}</h4>
      <button @click="deleteTodo(todo.id)">Delete</button>
    </div>
  </section>
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
  display: flex;
  align-items: center;
  justify-content: space-between;
}

button {
  border: none;
  background: transparent;
  font-size: 1rem;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}

button:hover {
  color: red;
}
</style>
