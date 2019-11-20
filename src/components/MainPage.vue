<template>
    <div class="card">
        <nav-bar></nav-bar>
        <div>
            <h1>This is Main Page</h1>
            <p>Max score</p>
            <p>Easy : {{MaxE}}</p>
            <p>Normal : {{MaxN}}</p>
            <p>Hard : {{MaxH}}</p>
        </div>
    </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import { EventBus } from "../plugins/event-bus.js";
export default {
    components: {
        NavBar,
    },
    createdE() {
        EventBus.$on('user-play-easy', (count) => (this.MaxE = count));
    },
    createdN() {
        EventBus.$on('user-play-normal', (count) => (this.MaxN = count));
    },
    createdH() {
        EventBus.$on('user-play-Hard', (count) => (this.MaxH = count));
    },
    data(){
        return{
            MaxE: 0,
            MaxN: 0,
            MaxH: 0
        }
    },
}
</script>