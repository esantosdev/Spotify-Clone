<template>
  <div id="player">
    <a>
      <span class="icon">
        <font-awesome-icon :icon="['far', 'heart']" />
      </span>
    </a>

    <router-link to="/player" class="music">
      <strong>{{music}} •</strong>
      {{artist}}
    </router-link>

    <a v-if="status === 'play'" @click="pause">
      <span class="icon">
        <font-awesome-icon icon="pause" />
      </span>
    </a>

    <a v-if="status === 'pause'" @click="play">
      <span class="icon">
        <font-awesome-icon icon="play" />
      </span>
    </a>

    <div class="progressBar">
      <div class="rangeBar" ref="rangeBar" style="width: 0%"></div>
    </div>
  </div>
</template>

<script>
import { setInterval } from "timers";
export default {
  data: () => ({
    status: "pause",
    music: "18 and life",
    artist: "Skid Row"
  }),
  methods: {
    play() {
      this.status = "play";
      const rangeBar = this.$refs.rangeBar;
      let progress = parseInt(rangeBar.style.width.replace("%"));
      setInterval(() => {
        progress = progress >= 100 ? 0 : progress + 1;
        rangeBar.style.width = `${progress}%`;
      }, 1000);
    },
    pause() {
      this.status = "pause";
    }
  }
};
</script>

<style lang="sass">
#player 
  position: fixed
  bottom: 48px
  width: 100%
  height: 48px
  display: flex
  justify-content: space-between
  background-color: #282828
  border-top: 1px solid #181818
  a
    text-align: center
    display: block
    height: 48px
    color: #c9c9c9
    text-decoration: none
    &.music 
        width: 70%
    
    .icon
      display: block
    
    .icon svg 
      height: 24px
      width: 64px
      margin: 10px
    strong 
        height: 48px
        line-height: 48px
  .progressBar
    position: absolute
    top: 0
    background-color: rgba(255, 255, 255, 0.2)
    width: 100%
    height: 1px
    .rangeBar
        background-color: #fff
        height: 1px
</style>