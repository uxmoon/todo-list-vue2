<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodosItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
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
