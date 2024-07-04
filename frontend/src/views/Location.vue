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
        location: []
        
    }
},
  methods: {

    getData(){
      // console.log(id)

      for (let data of json) {
        if (id == data.id) {
         this.title = data.title
         this.location = data 
        }
      }
    }

}
}



</script>

<template>
  <main>
    <div class="global-container"> Le titre de cette location est: {{ title }}
    </div>
    <div class="global-container"> L'id qu'on doit voit dans l'url est: {{ location.id }}
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


