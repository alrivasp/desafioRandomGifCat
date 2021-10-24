<template>
  <NavBar/>
  <Form/>
</template>

<script>
import NavBar from './components/NavBar.vue';
import Form from './components/Form.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    Form
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body{
  background-color: darkturquoise;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
