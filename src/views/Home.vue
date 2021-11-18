<template>
  <div class="home">
    <div v-for="bird in birds">
      <div class="card-text-center" style="width: 60rem;">
        <img v-bind:src="bird.image_url" class="card-img-top" v-bind:alt="bird.description">
        <div class="card-body">
          <h5 class="card-title">{{ bird.breed }}</h5>
          <p class="card-text"> {{ bird.description }} </p>
          <a href="#" class="btn btn-primary">More Info</a>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<style>


</style>

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