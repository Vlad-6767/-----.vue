<script setup>
import { ref } from 'vue'

const korzina = ref(0)

function reliz() {
  korzina.value += 1
}

defineExpose({ reliz })
</script>

<template>
  <header class="hader">
    <div class="haeder2">
      <img class="menu" src="/meny.svg" alt="Меню">
    </div>
    <div class="haeder2">
      <img class="menu" src="/person.svg" alt="Профиль">
    </div>
    <div class="haeder2">
      <img class="menu" src="/korz.svg" alt="Корзина">
      <p class="make">Товаров: {{ korzina }}</p>
    </div>
  </header>
</template>

<style scoped>
.hader {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 48px;
  width: 100%;
  min-height: 80px;
  padding: 0 24px;
  box-sizing: border-box;
  background-color: rgb(160, 155, 155);
  border-bottom: 1px solid black;
}

.haeder2 {

  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 12px;
  min-width: 0;
}

.menu {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  flex-shrink: 0;
  display: block;
  margin-bottom: 30px;
}

.make {
  margin: 0;
  font-size: 14px;
  white-space: nowrap;
  line-height: 1;
}

@media (max-width: 480px) {
  .hader {
    gap: 16px;
    min-height: 56px;
    height: auto;
    padding: 8px 12px;
    justify-content: space-evenly;
    align-items: center;
    overflow: hidden;
  }

  .haeder2 {
    gap: 12px;
    min-width: 0;
    align-items: center;
  }

  .menu {
    width: 28px;
    height: 28px;
    box-sizing: content-box;
    padding: 8px;
    margin: -8px;
  }

  .make {
    font-size: 12px;
    flex-shrink: 1;
    min-width: 0;
    overflow: hidden;
    text-overflow: ellipsis;
  }
}

@media (max-width: 360px) {
  .hader {
    gap: 8px;
    padding: 6px 8px;
  }

  .haeder2 {
    gap: 8px;
  }

  .menu {
    width: 24px;
    height: 24px;
    padding: 6px;
    margin: -6px;
  }

  .make {
    font-size: 11px;
  }
}
</style>