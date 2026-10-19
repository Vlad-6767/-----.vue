<script setup>
    import { ref } from 'vue';
    const korzina=ref(0)
    function reliz(){
        korzina.value+=1
    }
    defineExpose({reliz})
</script >
<template>
    <div class="hader">
        <div class="haeder2">
        <img class="menu" src="/meny.svg">
        <p class="text-header">Меню</p>
        </div>
        <div class="haeder2">
        <img class="menu" scr="/profil.svg">
        <p class="text-header">Профиль</p>
        </div>
        <div class="haeder2">
        <img class="menu" src="/korz.svg">
        <p class="text-header">Корзина</p>
        <p> Товаров:{{ korzina }}</p>
        </div>
    </div>
</template>

<style>
    .hader{
        gap: 100px;
        display: flex;
        width: 1000px;
        height: 100px;
        background-color:rgb(160, 155, 155);
        border:1px solid black;
        flex-direction: row ;
        width: 100%;
        justify-content: center;
        
    }
    .text-header{
        width: 50px;
        height: 30px;
        display: flex;
        flex-direction: row;  
        margin-top: 50px;
    }
    .menu{
        border-radius: 10px;
        width: 40px;
        height: 40px;
        margin-top: 40px;
    }
    .haeder2{
        gap: 10px;
        display: flex;
        flex-direction: row;
    }

</style>