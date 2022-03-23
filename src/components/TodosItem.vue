<template>
  <p class="todo-item">{{ todo.title }}</p>
</template>

<script>
export default {
  name: "TodosItem",
  props: ["todo"],
};
</script>

<style scoped>
.todo-item {
  padding: 1rem;
  background-color: #fff;
  margin-bottom: 0.25rem;
}
</style>
