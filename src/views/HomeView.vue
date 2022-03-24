<template>
  <div id="app" class="container">
    <TodosAdd v-on:add-todo="handleAdd" />
    <TodosList v-bind:todos="todos" v-on:del-todo="handleDelete" />
  </div>
</template>

<script>
import axios from "axios";
import TodosList from "../components/TodosList";
import TodosAdd from "../components/TodosAdd";

export default {
  name: "HomeView",
  components: {
    TodosList,
    TodosAdd,
  },
  data() {
    return {
      todos: [
        // {
        //   id: 1,
        //   title: "Todo 1",
        //   completed: true,
        // },
        // {
        //   id: 2,
        //   title: "Todo 2",
        //   completed: false,
        // },
        // {
        //   id: 3,
        //   title: "Todo 3",
        //   completed: false,
        // },
      ],
    };
  },
  methods: {
    handleDelete(id) {
      // add the 'id' at the end
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(() => (this.todos = this.todos.filter((todo) => todo.id !== id)))
        .catch((err) => console.log(err));

      // this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    handleAdd(newTodo) {
      // jsonplaceholder gives you an id
      const { title, completed } = newTodo;
      // post request and send data
      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title,
          completed,
        })
        .then((res) => (this.todos = [...this.todos, res.data]))
        .catch((err) => console.log(err));
      // this.todos = [...this.todos, newTodo]
    },
  },
  // lifecycle hook
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=4")
      // .then(res => console.log(res))
      .then((res) => (this.todos = res.data))
      .catch((err) => console.log(err));
  },
};
</script>
