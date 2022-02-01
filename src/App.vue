<template>
  <div id="app">
    <app-loader v-if="!flagLoaded" />
    <nav-bar 
    @genre="switchSelectGenre"
    @authors="switchSelectAuthors"
    />
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
    switchSelectGenre(event) {
      this.discoFiltered = this.discoList.filter((disco) => {
      return disco.genre.toLowerCase().includes(event.target.value);
      })
    },
    switchSelectAuthors(events) {
      this.discoFiltered = this.discoList.filter((disco) => {
      return disco.author.toLowerCase().includes(events.target.value);
      })
    }
  }
}
</script>

<style lang="scss">
@import './style/main.scss';
</style>