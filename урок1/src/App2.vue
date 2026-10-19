// Авторизация
<script setup>
import { ref } from "vue";
    
    const secretCode = ref("")
    const Name = ref("")
    const Status = ref('0')
    function AgentUser() {
        if (secretCode.value == "007" && Name.value == 'Agent'){
            Status.value = 1
        }
        else if(Name.value =="Agent" && secretCode.value !='007'){
            Status.value = 2
        }
        else{
            Status.value=3
        }

    }
</script>
<template>

    <input v-model="Name" placeholder="Введите имя">
    <input v-model="secretCode" placeholder="Введите код">
    <button @click = "AgentUser">Проверить</button>
    <h1 v-if ="Status==2 ">Неверный секретный код</h1>
    <h1 v-else-if ="Status==3 ">Вы не числитесь среди агентов</h1>
    <div v-else-if = 'Status==1'>
        <h1>Доступ разрешон,добро пожаловать ,агент!</h1>
    </div>
</template>