<template>
    <div class="card">
        <nav-bar></nav-bar>
        <div>
            <h1>This is Main Page</h1>
            <p>Max score</p>
            <b-table :data="scores" :columns="columns"></b-table>
        </div>
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
            ]
            // MaxE: 0,
            // MaxN: 0,
            // MaxH: 0
        }
    },
    computed: {
        ...mapState("scores", ["scores"])
    }
}
</script>