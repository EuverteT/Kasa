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
        <button>&uarr;</button>
    </div>
    <div>{{ equipments }}</div>
  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>