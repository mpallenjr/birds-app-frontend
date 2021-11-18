<template>
  <div class="new">
 <p> Breed:   <input type="text"> </p>
 <p> Location:   <input type="text"> </p>
 <p> Image:   <input type="text"> </p>
 <p> Description:   <input type="text"> </p>
<button type="button" class="btn btn-primary" v-on:click="newBirds()">Add Bird</button>
  </div>
</template>

<style></style>

<script>
  export default {
    methods: {
newBirds: function () {
  console.log('hello')
}
    },
  };
</script>