<template>
  <img alt="Vue logo" src="./assets/logo.png"><br>
  <button @click="showDogs()">Show Dogs</button><br>
  <div class="dog" v-for="dog in dogs" :key="dog.id">
 <img :src="dog" alt="">
  </div>
</template>

<script>

export default {
  name: 'App',
data() {
  return {
    dogs:[]
  }
},
methods: {
  showDogs() {
    fetch('https://dog.ceo/api/breeds/image/random')
    .then(res => res.json())
    .then(data => this.dogs = data)
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.dog {
margin-top: 50px;
}
</style>
