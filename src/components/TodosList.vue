<template>
  <div>
    <h1>Todos List</h1>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodosItem v-bind:todo="todo" />
    </div>
  </div>
</template>

<script>
import TodosItem from "./TodosItem.vue";

export default {
  name: "TodosList",
  components: { TodosItem },
  props: ["todos"],
};
</script>

<style scoped></style>
