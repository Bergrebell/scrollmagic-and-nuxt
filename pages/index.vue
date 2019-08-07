<template>
  <div class="container">
    <div :ref="`myDiv`" @mouseover="animateDiv">
      FOO
    </div>
  </div>
</template>

<script>
import TweenMax from 'gsap/umd/TweenMax'

export default {
  methods: {
    animateDiv() {
      const myDiv = this.$refs.myDiv
      TweenMax.killTweensOf(myDiv)
      TweenMax.to(myDiv, 0.5, { scaleX: -1 })
    }
  }
}
</script>

<style></style>
