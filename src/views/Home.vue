<template>
  <div class="home">
    <div v-for="bird in birds">
      <p> BREED:   {{ bird.breed }} </p>
      <p> LOCATION:   {{ bird.location }} </p>
      <p> <img v-bind:src="bird.image_url"> </p>
      <p> DESCRIPTION:   {{ bird.description }} </p>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from 'axios';
  export default {
    data: function () {
      return {
        birds: []
      };
    },
    created: function () {
      this.indexBirds();
    },
    methods: {
      indexBirds: function () {
        console.log('hello')
        axios.get("http://localhost:3000/birds").then(response => {
          console.log(response.data)
          this.birds = response.data
        })
      },
    },
  };
</script>