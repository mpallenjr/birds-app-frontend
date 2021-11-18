<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="bird in birds">
   <p> BREED:   {{ bird.breed }} </p>
   <p> LOCATION:   {{ bird.location }} </p>
   <p> IMAGE:   {{ bird.image }} </p>
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
        message: "Welcome to Vue.js!",
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