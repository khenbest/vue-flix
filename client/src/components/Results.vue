<template>
<v-app>
  <v-content>
    <div class="results">
 
    <div v-for="movie in movies" class="result" :key="movie.id">
       <img @click="viewDetails(movie)" :src="'https://image.tmdb.org/t/p/w200'+movie.poster_path" alt="">
        <h1>{{movie.title}}</h1>

        

    </div>
</div>
</v-content>
</v-app>
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

