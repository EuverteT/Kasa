<script>
export default{
    props: {
    description: String
}
}
</script>

<template>
  <div class="component">
    <div class="component-title">
        <div>Description</div>
        <button class="expand-button">&uarr;</button>
    </div>
    <div class="description">{{ description }}</div>
  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>