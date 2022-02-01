<template>
  <div id="app">
    <app-loader v-if="!flagLoaded" />
    <nav-bar
    @search="switchSelect" />
    <!-- @search="filterResults" 
    @reset="filterReset" -->
    <main-container :discoList="discoFiltered"/>
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
      discoFiltered:[],
      flagLoaded: false
    }
  },
  mounted() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((element) => {
      this.discoList = element.data.response,
      this.discoFiltered = element.data.response,
      this.flagLoaded = true;
    })
  },
  methods: {
    // filterResults (keyword) {
    //   this.discoFiltered = this.discoList.filter((disco) => {
    //     return disco.title.toLowerCase().includes(keyword);
    //   })
    // },
    // filterReset () {
    //   this.discoFiltered = this.discoList
    // }
    // filterResults (keyword) {
    //   this.discoFiltered = this.discoList.filter((disco) => {
    //     return disco.genre.toLowerCase().includes(keyword);
    //   })
    // }
    switchSelect(event) {
      this.discoFiltered = this.discoList.filter((disco) => {
      return disco.genre.toLowerCase().includes(event);
      })
    }
  }
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>