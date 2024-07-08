<script>
export default{

    data(){
      return {
        open: true
      }
    },

    props: {
      description: String
    }


}
</script>

<template>
  <div class="component">
    <div class="component-title">
        <div>Description</div>
        <button v-if="open" @click= "open = false" class="notExpand-button">&uarr;</button>
        <button v-if="!open" @click= "open = true" class="expand-button">&darr;</button>
    </div>
    <div class="description">
      <div v-if="open">{{ description }}</div>
    </div>
  </div>
  
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>