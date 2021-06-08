<template>
  <div>
    <h1>Counter</h1>
    <div>{{ countMessage }}</div>
    <button @click="count++">Click!!</button>
    <button @click="count = 0">Reset!!</button>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "Counter",
  setup() {
    const count = ref(0);
    const countMessage = computed(() => "Count: " + count.value);
    return { count, countMessage };
  },
};
</script>

<style></style>