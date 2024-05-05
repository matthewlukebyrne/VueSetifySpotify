<template>
  <div class="flex flex-col items-center justify-center min-h-screen">
    <h1 class="text-3xl font-bold mt-8 mb-8">Hello from Vue and Tailwind CSS!</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <Cards msg="Setlist FM and Spotify API to search and generate playlists."/>
    <!-- Use the DesignTest component and pass fileId and nodeId as props -->
  </div>
</template>

<script>
import Cards from './components/Cards.vue'
// import DesignTest from './components/DesignTest.vue'; // Ensure the path is correct

export default {
  name: 'App',
  components: {
    Cards,
    // DesignTest // Register the component
  },
  data() {
    return {
      // Set these to your actual Figma file ID and node ID
      fileId: 'bSeDGKAvdkTRqODt5ViraH', 
      nodeId: '19-8389'
    };
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
