<template>
  <p class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <input type="checkbox" v-on:change="handleCheck" :checked="todo.completed">
    {{ todo.title }}
    <button class="delete" v-on:click="$emit('del-todo', todo.id)">Delete</button>
  </p>
</template>

<script>
export default {
  name: "TodosItem",
  props: ["todo"],
  methods: {
    handleCheck() {
      // eslint-disable-next-line vue/no-mutating-props
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
  color: #fff;
  border: none;
  box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
}
</style>
