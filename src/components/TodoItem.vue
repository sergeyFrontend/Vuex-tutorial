<template>
  <div style="width: 250px; margin: 5px auto">
    <div style="display: flex; justify-content: space-between">
      <span :class="{ completed: todo.completed }" @click="toggleStatus(todo)">
        {{ todo.title }}</span
      >
      <button
        @click="deleteTodo(todo)"
        style="color: white; background: red; border: none"
      >
        Delete Todo
      </button>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  props: ["todo"],
  methods: {
    ...mapActions({
      deleteTodo: "deleteTodo",
      toggleStatus: "toggleStatus",
    }),
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>
