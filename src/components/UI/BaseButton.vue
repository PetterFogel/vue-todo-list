<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    mode: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.add-btn {
  width: 100%;
  font-size: 1.2rem;
  padding: 0.7rem;
  border-radius: 12px;
  color: #fff;
  font-weight: bold;
  background: #4caf50;
  border: none;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}
.add-btn:hover {
  background: #38813a;
}

.delete-btn {
  border: none;
  background: transparent;
  font-size: 1rem;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}

.delete-btn:hover {
  color: red;
}
</style>
