<template>
  <div>
    <input type="text" v-model="newTodoItem" style="margin-top: 50px" />
    <button @click="addNewTodoItem()">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    addNewTodoItem() {
      this.$store.dispatch("addNewTodo", this.newTodoItem);
      this.newTodoItem = "";
    },
  },
};
</script>
