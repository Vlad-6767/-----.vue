<script setup>
    import { ref } from "vue";
    
    const login = ref('')
    const password = ref('')
    const isLoggedIn = ref(false)

    function loginUser() {
        if (login.value == 'admin' && password.value == "admin") {
            isLoggedIn.value = true
        }
        console.log("Неуспешная авторизация")
    }
</script>

<template>
    <div v-if="!isLoggedIn">
        <h1 class="auth">Магазин</h1>
        <h3 class="Best">Лучшие товары</h3>
        <button @click="loginUser">Войти</button>
    </div>
    <h1 v-else>Добро пожаловать</h1>
</template>

<style lang="css" scoped>
    .auth {
        color: red;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }
    button {
        background-color:blue;
        margin-bottom: 10px;
        color: white;
        width: 60px;
        height:30px;
        border-radius: 4px;
        
    }
    div{
        border:1px solid black;
        border-radius: 10px;
        display:flex;
        width: 325px;
        flex-direction: column;
        align-items: center;
            
    }
    .Best{
        color: black;
        
    }

</style>