<template>
<v-app>
  <v-content>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
<!-- <HelloWorld msg="Welcome to vue flix!"/> -->

            <!-- this will search when form is submitted, using search method -->
<form @submit.prevent="search" class="mb-5">
<input  type="text" v-model="movieName" placeholder="Search movie">

  </form>


<Results :movieData="movies" v-on:viewDetails="setActiveMovie" class="col"/>
    <Details :movieDetails="activeMovie" class="col"/>



 </div>
 </v-content>
 </v-app>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Results from "@/components/Results.vue";

export default {
  name: "home",
  components: {
    HelloWorld,
    Results,
    data() {
      return {
        movieName: "",
        activeMovie: {}
      };
    }
  },
  computed: {
    // always watching for your mutations in the store.
    movies() {
      return this.$store.state.movies;
    }
  },

  methods: {
    search() {
      // action         // refers to movieName in v model & empty string in data
      this.$store.dispatch("search", this.movieName);
    },

    setActiveMovie(movie) {
      this.activeMovie = movie;
    }
  }
};
</script>

