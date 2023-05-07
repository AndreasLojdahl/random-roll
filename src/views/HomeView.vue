<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()

const maxPlayers = 9
const gameNameHeader = 'Random Roll'
const subHeader = 'Choose how many players'
</script>

<template>
  <div class="homeView">
    <p class="header courier-font-center">{{ gameNameHeader }}</p>
    <p class="subHeader courier-font-center">{{ subHeader }}:</p>

    <div class="gridContainer">
      <button
        class="button"
        v-for="n in maxPlayers"
        @click="() => router.push({ name: 'GameBoard', params: { numberOfPlayers: n + 1 } })"
      >
        {{ n + 1 }}
      </button>
    </div>
  </div>
</template>

<style scoped>
.homeView {
  display: flex;
  flex-direction: column;
}
.gridContainer {
  height: 50vh;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px 20px;
}
.header {
  color: white;
  font-size: xx-large;
  margin-bottom: 1rem;
}
.subHeader {
  color: white;
  font-size: large;
  margin-bottom: 3rem;
}
.button {
  font-size: xx-large;
  font-family: Courier;
  font-weight: bold;
  cursor: pointer;
  border-radius: 10px;
}
.button:hover {
  background-color: black;
  color: white;
  border: 2px solid white;
}

.courier-font-center {
  font-family: Courier;
  text-align: center;
}
</style>
