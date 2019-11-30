<template>
    <div class="card">
        <img src="https://dejpknyizje2n.cloudfront.net/svgcustom/clipart/preview/boom-graphic-comic-sticker-31105-300x300.png">
        <h1>Welcome to Bombed Field</h1>
        <nav-bar></nav-bar>
        <p>Live Score</p>
        <b-table class="primary" :data="scores" :columns="columns"></b-table>
    </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import { mapState } from "vuex";
export default {
    components: {
        NavBar,
    },
    data(){
        return{
            columns: [
                { field: "level", label: "level" },
                { field: "score", label: "score" },
            ],
        }
    },
    computed: {
        ...mapState("scores", ["scores"])
    }
}
</script>