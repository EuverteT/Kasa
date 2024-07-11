<script>
export default{

    data(){
      return {
        open: true
      }
    },
    props: {
      equipments: Array
    }
}
</script>

<template>
  <div class="component">
    <div class="component-title">
        <div>Equipements</div>
        <button v-if="open" @click= "open = false" class="notExpand-button">&uarr;</button>
        <button v-if="!open" @click= "open = true" class="expand-button">&darr;</button>
    </div>
    <div class="equipments">
      <div v-if="open" v-for="data in equipments">{{ data }}</div>
    </div>
  </div>
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>