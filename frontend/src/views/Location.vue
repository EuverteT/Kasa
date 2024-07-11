<script>

const currentPath = window.location.href
const id = currentPath.slice(31)

import json from '../assets/logements.json';
import Description from '../components/Description.vue'
import Equipments from '../components/Equipments.vue'

export default{

  name: "Location",
  components: {
    Description,
    Equipments,
  },

  created() {
    this.getData();
    this.displayPicture()
    
  },
  
  data(){
    return {
        myJson: json,
        id: "",
        data: [],
        test: "",
        index: "",
        arrayLength: ""      
    }
  },
  methods: {
    getData(){
      for (let data of json) {
        if (id == data.id) {
         this.data = data 
        }
      }
    },
    displayPicture(){
      for (let data of json) {
        if (id == data.id) {
         this.data = data

         let index = 0
         let arrayLength = data.pictures.length

         localStorage.setItem("index", index);
         localStorage.setItem("arrayLength", arrayLength);

         this.test = data.pictures[index]
        }
      }
    },
    
    displayNext(){
      for (let data of json) {
          if (id == data.id) {
            this.data = data
            let index = localStorage.getItem("index")
            let arrayLength = localStorage.getItem("arrayLength");
              if (index == (arrayLength-1)) {
                index = 0
                this.test = data.pictures[index]
                localStorage.setItem("index", index);
              }            
              else {
                index++
                this.test = data.pictures[index]
                localStorage.setItem("index", index);
              }
          }
      }
    },
    displayPrev(){
      for (let data of json) {
          if (id == data.id) {
            this.data = data
            let index = localStorage.getItem("index")
            let arrayLength = localStorage.getItem("arrayLength");
              if (index == 0) {
                index = (arrayLength-1)
                this.test = data.pictures[index]
                localStorage.setItem("index", index);
              }            
              else {
                index--
                this.test = data.pictures[index]
                localStorage.setItem("index", index);
              }
          }
      }
    }
  }

}

</script>

<template>
  <main>
    <div class="global-container">
      <div class="galery">
        <button v-if="(data.pictures.length) > 2" @click="displayPrev()"class="galeryBtnLeft">&larr;</button>
        <img class="galeryImg" :src="test">
        <button v-if="(data.pictures.length) > 2" @click="displayNext()" class="galeryBtnRight">&#x2192;</button>
      </div>
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
      <div class="bottom-container">
        <Description :description="data.description" />
        <Equipments :equipments="data.equipments" />
      </div>     
    </div>
  </main>
</template>

<style scoped lang="scss">
@import "../assets/main.scss";

.galery {
  @include flexRowJCCenter;
}

.galeryImg {
  width: 70%;
  height: 500px;
  @include small {
    width: 90%;
    height: 300px;
  }
  @include verySmall {
    width: 90%;
    height: 300px;
  }
}

.galeryBtnLeft,
.galeryBtnRight {
  background: none;
  border: none;
  color: black;
  font-size: 10rem;
  @include small {
    font-size: 3rem;
  }
  @include verySmall {
    font-size: 1.5rem;
  }
}

.global-container {
  @include flexColumn;
  color: $rouge;
  margin: 0 5rem;
  @include small {
    margin: 0 1rem;
  }
  @include verySmall {
    margin: 0 1rem;
  }
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
  @include flexRowJCBetween;
  @include small {
    flex-direction: column;
  }
  @include verySmall {
    flex-direction: column;
  }
}

.bottom-container {
  @include flexRowJCBetween;
  @include small {
    flex-direction: column;
    align-items: center;
  }
  @include verySmall {
    flex-direction: column;
    align-items: center;
  }
}

.hostAndRating-container {
  padding: 1rem;
  @include small {
    @include flexRowAICenter;
    justify-content: space-around;
  }
  @include verySmall {
    @include flexRowAICenter;
    justify-content: space-around;
  }
}

.host-container {
  @include flexRowAICenter;
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
  @include verySmall {
    flex-wrap: wrap;
  }
}

.tags {
  margin-right: 1rem;
  background-color: $rouge;
  color: white;
  border-radius: 0.5rem;
  padding: 0.2rem 0.5rem;
  @include verySmall {
    margin-right: 0.5rem;
    margin-bottom: 0.5rem;
  }
}
</style>


