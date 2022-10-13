<template>
  <base-card>
    <div>
      <input type="checkbox" />
      <h4>{{ todo.description }}</h4>
    </div>
    <base-button mode="delete-btn" @click="deleteTodo(todo.id)"
      >Delete</base-button
    >
  </base-card>
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

input {
  margin-right: 1rem;
  width: 1.2rem;
  height: 1.2rem;
}
</style>
