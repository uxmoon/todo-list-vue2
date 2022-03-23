<template>
  <div>
    <h1>Todos List</h1>
    <ul v-bind:key="todo.id" v-for="todo in todos">
      <li>{{todo.title}}</li>
    </ul>
  </div>  
</template>

<script>
export default {
  name: "TodosList",
  props: ["todos"]
}
</script>

<style scoped>
</style>