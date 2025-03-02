<script>
    import { ref, reactive, toRef, toRefs } from 'vue';

    export default {
        setup () {

            const message = ref('Hello From Vue 3 !');
            const quantity = ref('1');

            const increment = () => quantity.value ++;
            const decrement = () => quantity.value --;

            // Reactive object
            const item = reactive({
                name : 'Product 1',
                price : 100
            });

            const swapProduct = () => {
                item.name = "Product 2",
                item.price = "50"

                //console.log('toRefName', toRefName.value)
            }

            // toRef
            //const toRefName = toRef(item, 'name');

            //console.log('toRefName', toRefName.value)

            //item.name = 'Product 3';

            //console.log('toRefName', toRefName.value)
            // End toRef


            return {
                message,
                quantity,
                increment,
                decrement,
                item,
                swapProduct,
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

    <!-- Reactive -->
     <hr>
     <p>{{ item.name}} : {{ item.price }}</p>
     <button @click="swapProduct">Swap Product</button>
</template>


<style>
</style>
