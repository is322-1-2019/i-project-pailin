<template>
    <div class="card">
        <div>
            <minesweeper></minesweeper>
        </div>
    </div>
</template>

<script>
import Minesweeper from "./game/Minesweeper.vue"
export default {
    components: {
        Minesweeper
    }
}
</script>