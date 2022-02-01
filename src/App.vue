<template>
  <div id="app">
    <app-loader v-if="!flagLoaded" />
    <nav-bar />
    <main-container :discoList="discoList"/>
  </div>
</template>

<script>
import MainContainer from './components/MainContainer.vue'; 
import NavBar from './components/NavBar.vue'; 
import AppLoader from './components/AppLoader.vue';
import axios from 'axios'

export default {
  name: 'App',
  components: {
    AppLoader,
    NavBar,
    MainContainer,
  },
  data() {
    return {
      discoList:[],
      flagLoaded: false
    }
  },
  mounted() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((element) => {
      this.discoList = element.data.response,
      this.flagLoaded = true;
    })
  }
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>