<template>
  <div class="flex flex-col items-center justify-center min-h-screen">
    <h1 class="text-3xl font-bold mt-8 mb-8">Hello from Vue and Tailwind CSS!</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <Cards msg="Setlist FM and Spotify API to search and generate playlists."/>
  </div>
</template>

<script>
import Cards from './components/Cards.vue'

export default {
  name: 'App',
  components: {
    Cards
  }
}
</script>

<style>
#app {
  font-family: "Avenir", "Helvetica Neue", Helvetica, Arial, sans-serif; /* Avenir font family */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: linear-gradient(180deg, rgba(29, 185, 84, 0.2), rgba(29, 185, 84, 0.1)); /* Green gradient */
}

</style>
