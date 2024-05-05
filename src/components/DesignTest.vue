<template>
  <div>
    <!-- Display the image from Figma -->
    <img :src="imageUrl" alt="Figma Design Element" />
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'DesignTest',
  props: ['fileId', 'nodeId'],
  data() {
    return {
      imageUrl: null, // This will hold the image URL
      loading: true, // Tracks loading state
      error: null // Holds error information, if any
    };
  },
  methods: {
    fetchFigmaImage() {
      const url = `https://api.figma.com/v1/images/${this.fileId}?ids=${this.nodeId}&format=svg`;
      axios.get(url, {
        headers: {
          'X-Figma-Token': 'figd_giUYVbRKXkm-Ie0WwimqQJeu-Pg7cyOyZZYyners' // This should be kept secure
        }
      })
      .then(response => {
        const images = response.data.images;
        if (images && images[this.nodeId]) {
          this.imageUrl = images[this.nodeId]; // Set the image URL from the response
          this.error = null; // Reset error state
        } else {
          throw new Error('Image not found for the specified Node ID.');
        }
      })
      .catch(error => {
        this.error = 'Failed to fetch image: ' + (error.response ? error.response.data : error.message);
        console.error('Error fetching Figma image:', this.error);
      })
      .finally(() => {
        this.loading = false; // Update loading state
      });
    }
  },
  mounted() {
    this.fetchFigmaImage(); // Fetch the image when the component is mounted
  }
};
</script>


<style>
/* Add styles as needed */
</style>
