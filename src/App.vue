<template>
  <div id="app">


    <Header />

  
    <AlbumContainer />
    


  </div>
</template>

<script>

import Header from "./components/Header.vue"
import AlbumContainer from "./components/AlbumContainer.vue"
import "../src/style/general.scss"
// import { component } from 'vue/types/umd' QUESTO CHE COSA è?

export default {
  name: 'App',
  components: {
    Header,
    AlbumContainer
  }
}
</script>

<style lang="scss">



</style>
