<template>
    <div>
        <b-field>
            <b-button @click="easy">easy</b-button>
            <b-button @click="normal">normal</b-button>
            <b-button @click="hard">hard</b-button>
        </b-field>
        <div class="columns">
            <div class="column is-4" :key="poom.id" v-for="poom in pooms" id="state" @click="step" >{{ poom.value }}</div>
        </div> 
    </div>
</template>

<script>
export default {
    data() {
        return {
            lev: "",
            level: [
                {id:1,width:8,hight:8,bomb:20},
                {id:2,width:10,hight:10,bomb:30},
                {id:3,width:12,hight:12,bomb:40}
            ],
            pooms: [
                {id: 1 , value: "x"},
                {id: 2 , value: "2"},
                {id: 3 , value: "1"},
                {id: 4 , value: "2"},
                {id: 5 , value: "x"},
                {id: 6 , value: "1"},
                {id: 7 , value: "1"},
                {id: 8 , value: "1"},
                {id: 9 , value: "1"},
            ]
        }
    },
    methods: {
            easy() {
                this.level.id=1
                this.lev="easy"
                this.$buefy.notification.open('Level 1')
            },
            normal() {
                this.level.id=2
                this.lev="normal"
                this.$buefy.notification.open('Level 2')
            },
            hard() {
                this.level.id=3
                this.lev="hard"
                this.$buefy.notification.open('Level 3')
            },
            step() {
                
            },

        }
}
</script>

<style scoped>
    #state {
        color: rgb(173, 0, 0);
        background-color: darkgray;
    }
</style>