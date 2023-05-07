<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()

const maxPlayers = 8
const gameName = 'Random Roll'
</script>

<template>
  <div class="homeView">
    <p>{{ gameName }}</p>

    <button
      v-for="n in maxPlayers"
      @click="() => router.push({ name: 'GameBoard', params: { numberOfPlayers: n + 1 } })"
    >
      {{ n + 1 }}
    </button>
  </div>
</template>

<style>
.homeView {
  display: flex;
  flex-direction: column;
}
</style>
