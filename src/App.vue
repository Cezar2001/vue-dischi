<template>
  <div id="app">
    <main-container :discoList="discoList"/>
  </div>
</template>

<script>
import MainContainer from './components/MainContainer.vue'; 
import axios from 'axios'

export default {
  name: 'App',
  components: {
    MainContainer
  },
  data() {
    return {
      discoList:[]
    }
  },
  mounted() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
      this.discoList = response.data
    })
  }
}
</script>

<style lang="scss">

</style>
