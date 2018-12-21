<template>
  <div>
    <header>
      <div class="row">
        <h1>Multiply Defense</h1>
      </div>
    </header>
    <!--
    <img src="./assets/logo.png">
    <router-view/>
    -->
    <section id="game" class="row">
<game-scene></game-scene>
    </section>
  </div>
</template>

<script>
import GameScene from './GameSceneComponent'
export default {
  // name: 'App'
  components: {
    GameScene
  }
}
</script>

<style>
  /*
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
*/
  #game {
    position: relative;
    width: 300px;
    height: 480px;
    border: 1px solid black;
  }
</style>
