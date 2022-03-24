<template>
  <div class="todo-add">
    <form>
      <input type="text" name="title" placeholder="Add new todo..." />
      <input type="submit" value="Add" class="button" />
    </form>
  </div>
</template>

<script>
export default {
  name: "TodosAdd"
}
</script>

<style scoped>
  .todo-add {
    background-color: #fff;
    padding: 1rem;
    margin-bottom: 1rem;
  }
  form {
    display: grid;
    grid-template-columns: 1fr auto;
  }
</style>