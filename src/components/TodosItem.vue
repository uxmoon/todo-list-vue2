<template>
  <p class="todo-item" v-bind:class="{'is-complete':todo.completed}">{{ todo.title }}</p>
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

.is-complete {
  text-decoration: line-through;
}

.delete {
  background-color: #f00;
}
</style>
