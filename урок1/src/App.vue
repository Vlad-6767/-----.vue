<script setup>
import { ref } from 'vue'
import Header from './header.vue'
import Products from './Products.vue'

const headerRef = ref(null)

function addProduct() {
    headerRef.value.reliz()
}
</script>

<template>
    <Header ref="headerRef" />
    <Products @reliz="addProduct" />
</template>
