<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
<!-- <HelloWorld msg="Welcome to vue flix!"/> -->

            <!-- this will search when form is submitted, using search method -->
<form @submit.prevent="search">
<input type="text" v-model="movieName" placeholder="Search movie">
<h3>Searching for {{movieName}}</h3>
  </form>


<Results> :movieData="movies"</Results>



 </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Results from '@/components/Results.vue'

export default {
  name: 'home',
  components: {
    HelloWorld,
    Results,
    data(){
      return{
        movieName: ""
      }
    }
  },
computed:{ // always watching for your mutations in the store.
movies(){
  return this.$store.state.movies;
}
},

  methods:{
  search(){      // action         // refers to movieName in v model & empty string in data
    this.$store.dispatch("search", this.movieName) 
  }
  

  }




}
</script>

