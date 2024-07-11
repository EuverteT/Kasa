<script>
import json from '../assets/about.json';
import Banner from '../components/Banner.vue';

export default{

  components: {
    Banner
  },
  data(){
      return {
          myJson: json,
          data: [],
          aboutSrc: "src/assets/aboutBanner.png"
        }
    },
  methods: {
    closeText(data){
      document.getElementById(data.expandBtn).style.display = 'block'
      document.getElementById(data.name).style.display = 'none'
      document.getElementById(data.notExpandBtn).style.display = 'none'
    },
    openText(data){
      document.getElementById(data.expandBtn).style.display = 'none'
      document.getElementById(data.name).style.display = 'block'
      document.getElementById(data.notExpandBtn).style.display = 'block'
    }
  }
}
</script>

<template>
  <Banner :image="aboutSrc"/>
  <div class="about-container">
    <div class="component" v-for="data of myJson">
      <div class="component-title">
          <div>{{ data.title }}</div>
          <button :id=data.notExpandBtn @click= "closeText(data)" class="notExpand-button" >&uarr;</button>
          <button style="display: none" :id=data.expandBtn @click= "openText(data)" class="expand-button">&darr;</button>
      </div>
      <div :id=data.name class="description">
        <div>{{ data.text }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped lang=scss>
@import "./src/assets/main.scss";

.about-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.component {
  margin-bottom: 2rem;
  width: 90%;
  color: $rouge;
}

</style>
