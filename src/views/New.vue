<template>
 <div class="input-group input-group-lg">
  <p><span class="input-group-text" id="basic-addon1">Breed</span>
  <input type="text" class="form-control" placeholder="Breed" aria-label="Username" aria-describedby="basic-addon1" v-model="newBird.breed"></p>
  <p><span class="input-group-text" id="basic-addon1">Location</span>
  <input type="text" class="form-control" placeholder="Location" aria-label="Username" aria-describedby="basic-addon1" v-model="newBird.location"></p>
  <p><span class="input-group-text" id="basic-addon1">Image URL</span>
  <input type="text" class="form-control" placeholder="Link" aria-label="Username" aria-describedby="basic-addon1" v-model="newBird.image_url"></p>
  <p><span class="input-group-text" id="basic-addon1">Description</span>
  <input type="text" class="form-control" placeholder="Notes" aria-label="Username" aria-describedby="basic-addon1" v-model="newBird.description"></p>
  <button type="button" class="btn btn-primary" v-on:click="createBirds()">Add Bird</button>

</div>
</template>

<style></style>

<script>
import axios from 'axios';
  export default {
    data: function () {
      return {

        newBird: {}
      }

    },
    methods: {
createBirds: function () {
  console.log('add a bird')

axios.post("http://localhost:3000/birds", this.newBird).then(response => {
console.log(response.data)
this.$router.push("/");

})
}
    },
  };
</script>