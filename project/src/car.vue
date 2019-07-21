<template>
    <div class="styleForcar">
        <h3>Имя: {{autoName}} +Reverse Name {{revers}}</h3>
        <p>Год: {{carYear}}</p>
        <button v-on:click="changeName()">Кликни</button>
        <button v-on:click="changeFunc()">Кликни ещё</button>
        <button v-on:click="updateCounter()">Намжи ещё</button>
    </div>
</template>
<script>

    export default {
        props: {
            autoName: {
                type: String,
                default: 'Привет'//Если ничего не ввелено выласт Привет
            },


            carYear: Number,
            changeFunc: Function,
            counter: Number

        },

        methods: {
            changeName() {
                this.autoName = 'Mazda';
                this.$emit('namechange', this.autoName)
            },
            updateCounter() {
                this.$emit('counterUpdated', this.counter+1)
            }

        },


        computed: {
            revers() {
                return this.autoName.split('').reverse().join('')
            }
        }

    }
</script>
<style>
    .styleForcar {
        border: 1px solid red;
    }

    .styleForcar h3 {
        margin-bottom: 5px;
    }
</style>
