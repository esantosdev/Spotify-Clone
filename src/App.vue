<template>
  <div id="app">
    <router-view/>
      <Navbar />
      <Player />
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Player from './components/Player'


export default {
  components: {
      Navbar,
      Player
  } 

}

</script>


<style lang="sass">
* 
  margin: 0
  padding: 0
  box-sizing: border-box
html, body 
  height: 100%
#app
  height: 100%
  background-color: #000
  font-family: "Segoe UI", "Arial", sans-serif
</style>