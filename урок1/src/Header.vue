<script setup>
import { ref } from 'vue'

const korzina = ref(0)
const isCatalogOpen = ref(false)
const selectedCategory = ref('')

function toggleCatalog(){
  isCatalogOpen.value = !isCatalogOpen.value
}

function selectCategory(name) {
  selectedCategory.value = name
  isCatalogOpen.value = false
}

function reliz() {
  korzina.value += 1
}

defineExpose({ reliz })
</script>

<template>

  <header class="hader">
    <div class="haeder2">
      <img class="menu" src="/meny.svg" alt="Меню" @click="toggleCatalog">
    </div>
    <div class="haeder2">
      <img class="menu" src="/person.svg" alt="Профиль">
    </div>
    <div class="haeder2">
      <img class="menu" src="/korz.svg" alt="Корзина">
      <p class="make">Товаров: {{ korzina }}</p>
    </div>
    <div class="catalog" v-show="isCatalogOpen">
      <h3>Каталог товаров</h3>
      <button @click="selectCategory('Клавиатуры')">Клавиатуры</button>
      <button @click="selectCategory('Мышки')">Мышки</button>
      <button @click="selectCategory('Наушники')">Наушники</button>
    </div>
  </header>

  <p v-if="selectedCategory" class="selected">
    Вы выбрали: {{ selectedCategory }}
  </p>
</template>

<style scoped>
.hader {
  position: relative;
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
  cursor: pointer;
}

.make {
  margin: 0;
  font-size: 14px;
  white-space: nowrap;
  line-height: 1;
}

.selected {
  margin: 12px 24px;
  font-size: 16px;
  font-weight: 600;
  color: #222;
}

.catalog button {
  padding: 10px;
  background-color: #e5e5e5;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-align: left;
}
.catalog {
  position: absolute;
  top: 100%;
  left: 0;

  width: 220px;
  padding: 15px;

  background-color: white;
  border: 2px solid black;
  border-radius: 0 0 10px 0;

  display: flex;
  flex-direction: column;
  gap: 10px;

  z-index: 100;
  box-sizing: border-box;
}

.catalog button:hover {
  background-color: #cccccc;
  
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

@media (max-width: 480px) {
  .catalog {
    width: min(220px, 100%);
  }
}


</style>