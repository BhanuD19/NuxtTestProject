<template>
  <div class="container">
    <AppHeader />
    <nuxt />
  </div>
</template>

<script>
  import AppHeader from "../components/AppHeader";
  export default {
      components: {
          AppHeader
      }
  }
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0rem;
  padding: 0rem;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6rem;
  background: #f4f4f4;
}
a {
  color: #666;
  text-decoration: none;
}
ul {
  list-style: none;
}

.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: #fff;
}
</style>
