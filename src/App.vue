<script>
    import { ref } from 'vue';

    export default {
        setup () {

            const message = ref('Hello From Vue 3 !');
            const quantity = ref('1');

            const increment = () => quantity.value ++;
            const decrement = () => quantity.value --;


            return {
                message,
                quantity,
                increment,
                decrement,

            }
        }


    }

</script>

<template>
    {{ message }}
    <br>
    <input type="text" id="" v-model="message">
    <hr>

    <b>Quantity</b> : {{ quantity }}
    <br>
    <button @click="increment"> + </button>
    <button @click="decrement"> - </button>
</template>


<style>
</style>
