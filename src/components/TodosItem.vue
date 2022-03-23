<template>
  <p class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <input type="checkbox" v-on:change="handleCheck">
    {{ todo.title }}
  </p>
</template>

<script>
export default {
  name: "TodosItem",
  props: ["todo"],
  methods: {
    handleCheck() {
      this.todo.completed = !this.todo.completed
    }
  }
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
