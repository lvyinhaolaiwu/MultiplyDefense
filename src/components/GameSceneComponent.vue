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
      boxWidth: 50,
      boxHeight: 20,
      gameWidth: 300,
      gameHeight: 480,
      createjs: null,
      numberBoxes: []
    }
  },

  mounted () {
    this.init()
    this.generateNumberBox()
    this.stage.update()
  },

  methods: {
    init () {
      this.createjs = window.createjs
      this.canvas = document.getElementById('canvas')
      // this.stage = new window.createjs.Stage(this.canvas)
      // var hello = new window.createjs.Text('Hello CreateJS', '18px', 'white')
      // this.stage.addChild(hello)
      // this.stage.update()
      this.stage = new this.createjs.Stage(this.canvas)
    },
    rectShape (width, height, style) {
      var obj = new this.createjs.Container()
      style = style || {}
      style.strokeWidth = style.strokeWidth || 0
      style.strokeColor = style.strokeColor || 0
      style.fillColor = style.fillColor || 'rgb(255, 0, 0, 1)'

      var shape = new this.createjs.Shape()
      shape.graphics.setStrokeStyle(style.strokeWidth).beginStroke(style.strokeColor).beginFill(style.fillColor).drawRect(0, 0, width, height)
      obj.addChild(shape)
      return obj
    },
    box () {
      return this.rectShape(this.boxWidth, this.boxHeight, null)
    },
    numberBox (value) {
      var boxObj = this.box()
      var text = new this.createjs.Text(value, '24px Impact', 'blue')
      text.textBaseline = 'middle'
      text.textAlign = 'center'
      text.x = this.boxWidth / 2
      text.y = this.boxHeight / 2
      boxObj.addChild(text)
      return boxObj
    },
    randomInt (min, max) {
      return Math.floor(Math.random() * (max - min + 1) +
        min)
    },
    generateNumberBox () {
      var value = this.randomInt(1, 12) * this.randomInt(1, 12)
      var box = this.numberBox(value)
      box.x = Math.random() * (this.gameWidth - this.boxWidth)
      box.y = 0
      this.stage.addChild(box)
      this.numberBoxes.push(box)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#canvas{
  background: #333;
}
</style>
