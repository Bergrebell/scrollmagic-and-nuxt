<template>
  <div class="container">
    <div id="block">
      Hi there !
    </div>
  </div>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import ScrollToPlugin, { TweenMax } from 'gsap/umd/TweenMax'

export default {
  mounted() {
    const scene2 = this.$scrollmagic
      .scene({
        // ID of element where animation starts
        triggerElement: '.container',

        // {0,0.5,1} - animations starts from {top,center,end} of window
        triggerHook: 0.5,

        // Duration of animation
        duration: 300
      })

      // Declaration of animation and attaching to element
      .setTween('#block', {
        css: {
          backgroundColor: 'blue'
        },
        scale: 0.7 // the tween durtion can be omitted and defaults to 1
      })
      // Helpful tags for orientation on the screen
      .addIndicators({ name: '2 (duration: 300)' })

    // Add Scene to controller
    this.$scrollmagic.addScene(scene2)
  }
}
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: aliceblue;
}

.container {
  margin: 55vh 0;
  padding: 50px;
  outline: 1px dashed orange;
}

#block {
  padding: 10px;
  border: 1px solid black;
  font-family: Helvetica;
}
</style>
