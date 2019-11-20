<template>
    <div>
        <nav-bar></nav-bar>
        <b-field>
            <p>This is your luck : {{count}}</p>
        </b-field>
        <div class="columns is-multiline">
            <b-button 
                class="column is-2 state" 
                :key="poom.id" 
                v-for="poom in pooms"
                @click="step(poom)">
                    <p v-show="poom.showValue">{{ poom.value }}</p>
                </b-button>
        </div> 
    </div>
</template>

<script>
import NavBar from "../NavBar.vue";
import { EventBus } from "../../plugins/event-bus.js";
export default {
    mounted(){
        for(var j=0;j<20;j++){
            this.bombPosition.push(Math.floor(Math.random()*83));
        }
        this.bombPosition.sort();
        for(var i=0;i<48;i++){
            this.pooms.push({id: i+1 , value: '0' , showValue: false});
        }
        this.bombPosition.forEach(b=>{
            this.pooms[b].value='x';
        })
    },
    components: {
        NavBar
    },
    data() {
        return {
            pooms: [],
            bombPosition: [],
            count: 0,
        }
    },
    methods: {
        step(poom) {
            poom.showValue=true
            this.count=this.count+1
            if(poom.value==="x"){
                this.pooms.forEach(poom => poom.showValue=true)
                this.$buefy.notification.open('BOMBED!!')
                this.count.fireChanges()
                return
            }
        },
        fireChanges() {
            EventBus.$emit("user-play-easy", this.count);
        }
    }
}
</script>

<style scoped>
    .state {
        color: black;
        background-color: darkgray;
    }
</style>