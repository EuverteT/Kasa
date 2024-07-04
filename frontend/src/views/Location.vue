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
        data: []
        
    }
},
  methods: {

    getData(){
      // console.log(id)

      for (let data of json) {
        if (id == data.id) {
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

      <div class="mid-container">
    
        <div class="info-container">
          <div class="title">{{ data.title }}</div>
          <div class="location">{{ data.location }}</div>
          <div class="tags-container">
            <div class="tags" v-for="tag in data.tags">{{ tag }}</div>
          </div>
        </div>

        <div class="hostAndRating-container">
          <div class="host-container">
            <div class="host">{{data.host.name}}</div>
            <img :src="data.host.picture" />
          </div>
          <div class="rating">{{ data.rating }} étoiles</div>
        </div>
      </div>
      
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

.mid-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.hostAndRating-container {

}

.host-container {
  display: flex;
  flex-direction: row;
  align-items: center;

  .host {
    margin-right: 1rem;
  }

  img {
    height: 50px;
    width: 50px;
    border-radius: 2rem;
  }

}


.title {
  font-size: 2rem;
  font-weight: 800;
}

.tags-container {
  display: flex;
  flex-direction: row;
  margin: 1rem 0;
}

.tags {
  margin-right: 1rem;
  background-color: $rouge;
  color: white;
  border-radius: 0.5rem;
  padding: 0.2rem 0.5rem;
}

</style>


