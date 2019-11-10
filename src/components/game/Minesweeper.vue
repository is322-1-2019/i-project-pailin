<template>
    <div class="card-content">
        <b-flex>
            <b-button @click="easy">easy</b-button>
            <b-button @click="normal">normal</b-button>
            <b-button @click="hard">hard</b-button>
        </b-flex>
        <p>level : {{level}}</p>
        <b-flex>
            <b-button id="state" @click="vanich">x</b-button>
        </b-flex>
    </div>
</template>

<script>
export default {
    data() {
        return {
            level: 1
        }
    },
    methods: {
            easy() {
                this.level=1
                this.$buefy.notification.open('Level 1')
            },
            normal() {
                this.level=2
                this.$buefy.notification.open('Level 2')
            },
            hard() {
                this.level=3
                this.$buefy.notification.open('Level 3')
            },
            vanich() {
                
            }
        }
}
</script>

<style scoped>
    #state {
        color: darkgrey;
        background-color: darkgray;
    }
</style>