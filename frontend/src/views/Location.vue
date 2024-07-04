<script>
const currentPath = window.location.href
// console.log(currentPath)

const id = currentPath.slice(31)
// console.log(id)


import json from '../assets/logements.json';

export default{


  name: "Location",

  created() {
    this.getData();
  },
  data(){
    return {
        myJson: json,
        id: "",
        title: "",
        data: []
        
    }
},
  methods: {

    getData(){
      // console.log(id)

      for (let data of json) {
        if (id == data.id) {
         this.title = data.title
         this.data = data 
        }
      }
    }

}
}



</script>

<template>
  <main>
    <div class="global-container">
      <img :src="data.cover"/>
      
      <div class="title">{{ data.title }}</div>
      
      <div class="location">{{ data.location }}</div>
      
    </div>



  </main>
</template>

<style scoped lang="scss">
@import "../assets/main.scss";

.global-container {
  display: flex;
  flex-direction: column;
  color: $rouge;
  margin: 0 5rem;

}


img {
  max-height: 400px;
  align-self: center;
  width: 100%;
  object-fit: cover;
  border-radius: 0.5rem;
  margin-bottom: 1rem;

}

.title {
  font-size: 2rem;
  font-weight: 800;
}

</style>


