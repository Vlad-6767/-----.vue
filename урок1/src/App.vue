<script setup>
import { ref } from 'vue'
import Header from './Header.vue'
import Products from './Products.vue'
import futter from './futter.vue'

const headerRef = ref(null)

function addProduct() {
    headerRef.value.reliz()
}
</script>

<template>
    
    <Header ref="headerRef" />
    <Products @reliz="addProduct" class="Product"/>
    <futter futtter />
</template>

<style>
    .Product{
        margin-top: 20px;
        margin-bottom: 20px;
    }
</style>