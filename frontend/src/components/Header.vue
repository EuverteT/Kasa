<script setup>
import { RouterLink } from 'vue-router'
import HeureCourante from '../components/HeureCourante.vue';

</script>

<template>
  <div class="header">
    <img alt="Logo Kasa" class="logo" src="@/assets/kasa.png" width="125" height="50" />

  <nav>
    <RouterLink to="/">Accueil</RouterLink>
    <RouterLink to="/about">A propos</RouterLink>
    <HeureCourante />
  </nav>

  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 1rem;

  @include verySmall {
    flex-direction: column;
  }

  nav  {
    display: flex;
    flex-direction: row;
    align-items: center;

    @include verySmall {
    flex-direction: column;
    }

    a {
      font-size: 1.5rem;
      font-weight: 800;
      padding: 0.8rem;
      margin: 0 1rem;
      background: $mid-grey;
      border-radius: 0.5rem;

      @include verySmall {
        padding: 0.3rem;
        margin: 0.3rem 0;

      }

      &:hover {
      background: $hard-grey;

    }

    }
    

    

  }
}

</style>