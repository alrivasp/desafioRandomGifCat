<template>
  <div class="navBar__title">
      <h1>{{title}}</h1>
  </div>
</template>

<script>
export default {
    name: 'NavBar',
    data(){
        return {
            title: 'Random Gif Cat'
        }
    }
}
</script>

<style scoped>
.navBar__title{
    background-color: darkturquoise;
}
</style>
