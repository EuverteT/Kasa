<script>
const currentPath = window.location.href
console.log(currentPath)

const urlParams = new URLSearchParams(currentPath);
const idne = urlParams.get('location/');
console.log(idne)

import json from '../assets/logements.json';




export default{
    name: "Location",

    data(){
        return {
            id: localStorage.getItem("locationId"),
            myJson: json,
            usedUrl: window.location.search
        }
    },
    created() {
        this.getUrl();
    },
    methods: {
        getUrl(){
        
        console.log("test")
        
    }
    }

}


</script>




<template>
  <main>
    <div class="global-container">TEST
      
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


