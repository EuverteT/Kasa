<script>


export default{
    name: "Banner",

    data(){
      return {
      
      aboutSrc: "src/assets/aboutBanner.png",
      homeSrc: "src/assets/homeBanner.png"
      
      }
      
    },
    props: {
      image: String
    }
    
}
</script>

<template>
  <div class="banner">
    <img :src=image >
  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

.banner {
    display: flex;
    justify-content: center;
    margin: 1rem;
}

.banner img {
    width: 100%;
    object-fit: cover;
}

</style>