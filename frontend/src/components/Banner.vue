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
    <span>Chez vous, partout et ailleurs</span>
  </div>
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";
.banner {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  margin: 1rem;

  span {
    color: white;
    position: absolute;
    font-size: 3rem;

    @include verySmall {
    font-size: 1.5rem;
    }
    @include small {
    font-size: 2rem;
    }

  }
}

.banner img {
  width: 100%;
  object-fit: cover;
  filter: brightness(0.6);
  border-radius: 1rem
}
</style>