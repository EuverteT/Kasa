<script>
export default{
    name: "AboutBanner"

}
</script>

<template>
  <div class="banner">
    <img src="../assets/aboutBanner.png" />
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