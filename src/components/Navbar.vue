<template>
  <div id="navbar">
      <router-link to="/" :class="{active: menuActive === search}" @click="menuActive = 'search'">
          <span class="icon">
               <font-awesome-icon icon= "search"> </font-awesome-icon>
               <span class="title">Buscar</span>
          </span>   
      </router-link>

      <router-link to="/" :class="{active: menuActive === 'download'}" @click="menuActive = 'download'">
          <span class="icon">
               <font-awesome-icon :icon= "['fab', 'spotify']" />
               <span class="title">Baixar aplicativo</span>
          </span>   
      </router-link>
  </div>
</template>

<script>
export default {
   data: () => ({
       menuActive: 'search'
   })
}

</script>


<style lang="sass">
#navbar
  position: fixed
  bottom: 0
  width: 100%
  height: 48px
  display: flex
  justify-content: space-around
  background-color: #282828
  border-top: 1px solid #181818


a
 text-align: center
 display: block
 height: 48px
 color: #c9c9c9
 text-decoration: none
 padding: 4px 8px 2px

 &.active
  font-weight: bold
  color: #fff
  .title, .icon
  display: block
    
.title
 font-size: 11px

.icon svg
  height: 20px

</style>


