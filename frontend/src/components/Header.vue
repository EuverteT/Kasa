<script setup>
import { RouterLink } from 'vue-router'

</script>

<template>
    <img alt="Logo Kasa" class="logo" src="@/assets/kasa.png" width="125" height="50" />
      <nav>
        <RouterLink to="/">Accueil</RouterLink>
        <RouterLink to="/about">A propos</RouterLink>
      </nav>
</template>

<style>
</style>