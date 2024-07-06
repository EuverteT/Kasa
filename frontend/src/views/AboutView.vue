<script>

import json from '../assets/about.json';
import AboutComponent from '../components/AboutComponent.vue'

console.log(json)

</script>


<template>
  <AboutComponent v-for="item in myJson" />
</template>

<style>

</style>
