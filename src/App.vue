<template>
  <nav>
    <!-- v-for requires identical key for each block -->
    <template v-for="(item, idx) in routes" :key="idx">
      <span v-if="idx !== 0" class="nav-separator"> | </span>
      <router-link v-bind:to="item.path">{{ item.name }}</router-link>
    </template>
  </nav>
  <router-view />
</template>

<script setup>
import router from './router'

const routes = router.getRoutes()
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
