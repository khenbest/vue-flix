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

<!-- this is taking data from movies in computed and binding them to movie data in results, results will then create a prop called movieData to recieve it, this is a way of transferring data from parent component to child -->
<Results :movieData="movies" v-on:viewDetails="setActiveMovie" class="col"/>

<!-- this is taking the data from data.activeMovie which is just an empty object-->
    <Details :movieDetails="activeMovie" class="col"/>



 </div>
 </v-content>
 </v-app>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Results from "@/components/Results.vue";
import Details from "@/components/Details.vue";

export default {
  name: "home",

  data() {
    return {
      movieName: "",
      activeMovie: {}
    };
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
      console.log(movie);
    }
  },

  components: {
    HelloWorld,
    Results,
    Details
  }
};
</script>

