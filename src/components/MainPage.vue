<template>
    <div class="card">
        <nav-bar></nav-bar>
        <minesweeper></minesweeper>
    </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import Minesweeper from "./game/Minesweeper.vue"
export default {
    components: {
        Minesweeper,
        NavBar
    }
}
</script>