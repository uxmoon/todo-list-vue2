<template>
  <div class="todo-add">
    <form v-on:submit="handleSubmit">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add new todo..."
      />
      <input type="submit" value="Add" class="button" />
    </form>
  </div>
</template>

<script>
import {v4 as uuidv4} from "uuid";
export default {
  name: "TodosAdd",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    handleSubmit(event) {
      event.preventDefault();
      // build new todo object
      const newTodo = {
        id: uuidv4(),
        title: this.title,
        completed: false,
      };
      // Send up to parent component
      this.$emit("add-todo", newTodo);
    },
  },
};
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
