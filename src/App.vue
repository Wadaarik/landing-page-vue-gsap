<template>
  <div class="container">
    <Nav/>
    <Content/>
  </div>
</template>

<script>
import Nav from "@/components/Nav";
import Content from "@/components/Content";

export default {
  name: 'App',
  components: {
    Content,
    Nav
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  height: 100vh;
  background: #bebeb8;
}
</style>
