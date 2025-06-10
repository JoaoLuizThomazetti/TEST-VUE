<template>
    <div class="customCard">
        <!-- <h1>Custom Card Component</h1> -->
        <div class="cardInfo">
            <h2>Name: {{ product.name }}</h2>
            <h2>Code: #{{ product.code }}</h2>
            <h2>Stock: {{ stock }}</h2>
            <div class="stockControls">
                <button @click="raiseStock">+</button>
                <button @click="lowerStock">-</button>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { defineProps } from 'vue';
    const props = defineProps({
        product: {
            type: Object,
            required: true
        }
    });
    // import { reactive } from 'vue';
    // const product = reactive({
    //     name: 'Custom Product',
    //     code: 'CP001',
    //     stock: 0
    // });
    // function raiseStock() {
    //     product.stock++;
    // }
    // function lowerStock() {
    //     if (product.stock > 0) {
    //         product.stock--;
    //     }
    // }
    import { ref } from 'vue';
    const stock = ref(0);
    function raiseStock() {
        stock.value++;
    }
    function lowerStock() {
        if (stock.value > 0) {
            stock.value--;
        }
    }
</script>

<style scoped>
.customCard {
    background-color: white;
    padding: 15px;
    margin: 15px;
    border-radius: 6px;
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5);
    text-align: center;
    color: black;
}

.customCard:hover {
    transform: scale(1.04);
    z-index: 10;
    box-shadow: 0 8px 20px rgba(0, 155, 182, 0.5);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.cardInfo {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    font-size: 14px;
}
.stockControls {
    display: flex;
    flex-direction: column;
    justify-content: left;
    margin-left: -200px;
}
</style>