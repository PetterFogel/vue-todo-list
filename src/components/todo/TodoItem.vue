<template>
  <base-card>
    <div>
      <input type="checkbox" id="isDone" name="isDone" v-model="isTodoDone" />
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
      isDone: {
        type: Boolean,
        required: true,
      },
    },
  },
  data() {
    return {
      isTodoDone: this.todo.isDone,
    };
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
