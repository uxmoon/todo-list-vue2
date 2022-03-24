<template>
  <header class="header">
    <h1>Todo List</h1>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>    
  </header>
</template>

<script>
export default {
  name: 'HeaderApp'
}
</script>

<style scoped>
  .header {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
  }

  .header a {
    color: #fff;
    text-decoration: none;
  }

  .header a:hover {
    text-decoration: underline;
  }
</style>