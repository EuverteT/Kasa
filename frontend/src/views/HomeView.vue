<script>
import json from '../assets/logements.json';

export default{
    data(){
        return {
            myJson: json
        }
    }
}

</script>

<template>
  <main>
    <RouterLink to="/test">Page de test</RouterLink>
    <div class="global-container">
      <div class="card-container" v-for="data in myJson">
      
      <img :src="data.cover" height="200px" width="200px"/>
      <div> {{ data.title }}</div>

      </div>

    </div>


  </main>
</template>

<style scoped>
.global-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 80%
}
.card-container{
  border: 1px solid black;
  margin: 1rem;
}

</style>
