<template>
  <div class="container">
    <minesweeper></minesweeper>
  </div>
</template>

<script>
// import MainPage from './components/MainPage.vue'
import Minesweeper from './components/game/Minesweeper.vue'

export default {
  name: 'app',
  components: {
    // MainPage,
    Minesweeper
  }
}
</script>

