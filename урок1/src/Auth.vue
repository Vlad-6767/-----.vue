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
        <h1 class="auth">Авторизация</h1>
        <input v-model="login" placeholder="Введите логин">
        <input v-model="password" placeholder="Введите пароль">
        <button @click="loginUser">Войти</button>
    </div>
    <h1 v-else>Добро пожаловать</h1>
</template>

<style lang="css" scoped>
    .auth {
        color: blue;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        margin-left:10px
    }
    input {
        margin-left: 40px;
        border: 1px solid grey;
        border-radius :5px;
        width: 200px;
        height: 20px;
        margin-bottom: 20px;
        
    }
    button {
        background: rgb(3, 121, 3);
        color: white;
        width: 60px;
        height:30px;
        border-radius: 4px;
        margin-bottom: 30px;
        margin-left: 40px;
        
    }
    div{
        border:1px solid black;
        border-radius: 10px;
        display:flex;
        width: 325px;
        flex-direction: column;
            
    }

</style>