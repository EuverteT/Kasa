<script>
import json from '../assets/logements.json';
import Banner from '../components/Banner.vue';

export default{
  
  components: {
    Banner
  },

  data(){
    return {
      myJson: json,
      homeSrc: "src/assets/homeBanner.png"

      }
    }
}

</script>

<template>
  <Banner :image="homeSrc"/>
  <main>
    <div class="global-container">
      <a class="card-container" v-for="data in myJson" 
      :href="'http://localhost:5173/location/' + data.id">
      
      <img :src="data.cover"/>
      <div class="homeCardTitle"> {{ data.title }}</div>
      </a>

    </div>


  </main>
</template>

<style scoped lang="scss">
@import "../assets/main.scss";

.homeCardTitle {
  height: 20%;
  align-content: center;
}

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
  display: flex;
  flex-direction: column;

}

img {
  height: auto;
  width: 100%;
  height: 80%;
}

</style>
