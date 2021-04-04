<template>
    <div id="home">
    <div class="search">
      <router-link to="/configs" class="config">
        <span class="icon">
          <font-awesome-icon :icon="['far', 'sun']" />
        </span>
      </router-link>

      <h1>Olá!</h1>
      <p>Procure algo que você gosta e comece a curtir a música.</p>
      <a href="/search" class="button">
        <font-awesome-icon icon="search" />
        <span>Buscar</span>
      </a>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}

</script>

<style lang="sass">
#home
  height: 100%
  position: relative
  .search
    background-image: linear-gradient(48.366deg, rgb(80, 155, 245), rgb(175, 40, 150))
    display: flex
    flex-direction: column
    justify-content: flex-end
    color: #fff
    position: absolute
    top: 0
    height: 50%
    width: 100%
    text-align: center
    &::after
      background-image: linear-gradient(rgba(18, 18, 18, 0), rgb(18, 18, 18))
      content: ""
      height: 100%
      left: 0px
      position: absolute
      top: 0px
      width: 100%
    .config
      position: absolute
      top: 16px
      right: 8px
      color: #fff
      padding: 8px
      svg 
        height: 24px
        width: 24px
    h1, p, a
      z-index: 1
      font-weight: bold
    
    h1
      margin: 0 32px 6px
      font-size: 2.7em
    p
      margin: 0 32px 32px
    
    a.button
      background-color: rgb(255, 255, 255)
      display: flex
      height: 48px
      justify-content: center
      border-width: 1px solid transparent
      border-image: initial
      border-radius: 4px
      margin: 0px 16px
      padding: 0px
      line-height: 48px
      text-decoration: none
      color: #222
      svg 
        margin: 10px 6px 0 0 
        height: 24px
        width: 24px
</style>

