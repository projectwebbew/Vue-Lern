<template>
    <h1>{{counterfromapp}}</h1>
</template>

<script>
    import {eventEmiter} from "./main";

    export default {
        data() {
            return {
                counterfromapp: 0
            }
        },
        created() {
            eventEmiter.$on('counterUpdated',()=>{
                this.counterfromapp++
            })
        }
    }
</script>

<style scoped>

</style>