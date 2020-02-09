<template>
    <div class="header">
        <h1>Todo List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    </div>
</template>

<script>
export default {
    name:"Header"
}
</script>

<style scoped>
.header {
  background-color: rgb(73, 0, 0);
    color: #fff;
    text-align: center;
    padding: 10px;
  }
  
  .header a {
    color: rgb(139, 138, 138);
    text-decoration: none;
  }

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: orange;
}

#nav a.router-link-exact-active {
  color: yellow;
}
</style>