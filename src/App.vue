<template>
  <div id="app">
    <nav-bar />
    <main-container :discoList="discoList"/>
  </div>
</template>

<script>
import MainContainer from './components/MainContainer.vue'; 
import NavBar from './components/NavBar.vue'; 
import axios from 'axios'

export default {
  name: 'App',
  components: {
    MainContainer,
    NavBar
  },
  data() {
    return {
      discoList:[]
    }
  },
  mounted() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((element) => {
      this.discoList = element.data.response
    })
  }
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>