<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
<!-- <HelloWorld msg="Welcome to vue flix!"/> -->


<form>
<input type="text" v-model="movieName" placeholder="Search movie">
<h3>Message is: {{message}}</h3>
  </form>



 </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
