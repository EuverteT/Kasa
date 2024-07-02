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
    <div class="global-container">
      <div class="card-container" v-for="data in myJson">
      
      <img :src="data.cover"/>
      <div> {{ data.title }}</div>

      </div>

    </div>


  </main>
</template>

<style scoped lang="scss">
@import "../assets/main.scss";

.global-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  text-align: center;

}
.card-container{
  border: 1px solid black;
  margin: 1rem;
  width: 25%;
  border-radius: 0.5rem;
  background-color: $rouge;
  color: white;
}

img {
  height: auto;
  width: 100%;
  height: 80%;
}

</style>
