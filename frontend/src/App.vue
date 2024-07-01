<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img alt="Logo Kasa" class="logo" src="@/assets/kasa.png" width="125" height="50" />

    <div class="wrapper">

      <nav>
        <RouterLink to="/">Accueil</RouterLink>
        <RouterLink to="/about">A propos</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

</style>
