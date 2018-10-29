<template>
    <div class="results">
 
    <div v-for="movie in movies" class="result" :key="movie.id">
       <img @click="viewDetails(movie)" :src="'https://image.tmdb.org/t/p/w200'+movie.poster_path" alt="">
        <h4>{{movie.title}}</h4>

    </div>
</div>
</template>

<script>
export default {
  name: "Results",
  data() {
    return {};
  },
  methods: {
    viewDetails(movie) {
      this.$emit("viewDetails", movie);
    }
  },

  computed: {
    movies() {
      return this.$store.state.movies;
    }
  },
  props: ["movieData"]
};
</script>

