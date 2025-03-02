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

            // toRefs Logic
            const toRefsItem = toRefs(item);

            console.log('toRefsItem Name', toRefsItem.name.value)
            console.log('toRefsItem Price', toRefsItem.price.value)

            // toRefs Real Use
            const { name , price } = toRefs(item);


            return {
                message,
                quantity,
                increment,
                decrement,
                item,
                swapProduct,
                name,
                price
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
     <p>{{ name}} : {{ price }}</p>
     <button @click="swapProduct">Swap Product</button>
</template>


<style>
</style>
