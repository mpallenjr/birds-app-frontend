<template>
  <div class="show">
    <p> {{ showBirds }} </p>
  </div>
</template>

<style></style>

<script>
import axios from 'axios';
  export default {
    data: function () {
      return {
       showBirds: []
      };
    },
    created: function () {
      
      axios.get(`http://localhost:3000/birds/${this.$route.params.id}`).then(response => {
        console.log(this.$route);
        console.log(response.data);
        this.showBirds = response.data
      })
    },
    methods: {
    },
  };
</script>