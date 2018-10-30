
<template>
  <div class="details">
    <h1>Details</h1>
    <img :src="'https://image.tmdb.org/t/p/w200'+movieDetails.poster_path" alt="">
    <h2>{{movieDetails.title}}</h2>
    <p>{{movieDetails.overview}}</p>
    <p>details test</p>
  </div>
</template>
<script>
export default {
  name: "Details",
  data() {
    return {};
  },
  // this is recieving the movieDetails data from home.vue
  props: ["movieDetails"]
};
</script>
<style>
</style>