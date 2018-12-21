<template>
  <div>
<canvas id="canvas" width="300" height="480">

</canvas>
  </div>
</template>

<script>
export default {
  // name: 'HelloWorld',
  data () {
    return {
      // msg: 'Welcome to Your Vue.js App'
      stage: null,
      canvas: null,
      // boxWidth: 50,
      // boxHeight: 20,
      // gameWidth: 300,
      // gameHeight: 480,
      // createjs: null,
      // numberBoxes: []
    }
  },

  mounted () {
    this.canvas = document.getElementById('canvas')
    this.stage = new window.createjs.Stage(this.canvas)
    var hello = new window.createjs.Text('Hello CreateJS', '18px', 'white')
    this.stage.addChild(hello)
    this.stage.update()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#canvas{
  background: #333;
}
</style>
