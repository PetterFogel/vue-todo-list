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
.primary {
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
.primary:hover {
  background: #38813a;
}

.secondary {
  font-size: 1rem;
  padding: 0.7rem;
  border-radius: 12px;
  border: none;
  cursor: pointer;
  margin-bottom: 1rem;
  transition: all 200ms ease-in-out;
}

.delete {
  border: none;
  background: transparent;
  font-size: 1rem;
  cursor: pointer;
  transition: all 200ms ease-in-out;
}

.delete:hover {
  color: red;
}
</style>
