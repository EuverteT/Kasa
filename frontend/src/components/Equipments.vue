<script>
export default{
    props: {
    equipments: Array
}
}
</script>

<template>
  <div class="component">
    <div class="component-title">
        <div>Equipements</div>
        <button class="expand-button">&uarr;</button>
    </div>
    <div class="equipments">
      <div v-for="data in equipments">{{ data }}</div>
    </div>
  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>