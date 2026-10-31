<script setup> 
    import { disposeEmitNodes } from 'typescript';
import { ref } from 'vue';
    const emit =  defineEmits(['reliz'])
</script>
<template>

    <div class="glaven">
        <div class="glav">
            <div v-for="i in 9" :key="i" class="keyBoard1">
                <img src="https://ekt-basket-cdn-12.geobasket.ru/vol11102/part1110231/1110231413/images/big/1.webp" alt="keyBoard">
                <div class="discription">
                    <p1 class="price">8906₽</p1>
                    <p2 class='keyboard' >Клавиатура магнитная с подсветкой</p2>
                    <p3 class='opisanie'>Модель: Mercury V60Pro XTAL Гарантийный срок: 1 год Артикул:1110231413</p3>
                </div>
                <button class="button1">В корзину</button>
            </div>
        </div>
    </div>

</template>
<style>
    .discription{
        margin-top: 15px;
        margin-left: 15px;
        margin-bottom:15px ;
        max-width: 275px;
        display: flex;
        flex-direction: column;
    }
    .keyBoard1{
        display: flex;
        flex-direction: column;
        border:2px solid black;
        border-radius: 20px;
        
    }
    img{
        height: 285px;
        width: 275px;
        margin-top: 10px;
        margin-left: 13px;
        margin-right: 10px;
        border-radius: 5px;
    }
    .price{
        color: rgb(9, 160, 187);
        font-size: x-large;
        font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }
    .button1{
        width: 250px;
        height: 30px;
        color: black;
        background-color: rgb(215, 227, 230);
        border-radius: 5px;
        margin-left: 25px;
        margin-bottom: 5px;
    }
    .keyboard{
        color: rgb(59, 123, 153);
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-size: larger;
    }
    .opisanie{
        color: rgb(38, 79, 100);
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    .glav{
        
        display: flex;
        flex-direction: row;
        gap: 50px;
        justify-content: center;
    }

    .glaven{
        display: flex;
        flex-direction:column;
        gap:15px;
    }
</style>

