<script>
export default{

    data(){
        return {
        myJson: json,
        open: true
        }
   
    }
    
}

</script>

<template>
  <div class="component">
    <div class="component-title">
        <div> {{ title }}</div>
        <button v-if="open" @click= "open = false" class="notExpand-button">&uarr;</button>
        <button v-if="!open" @click= "open = true" class="expand-button">&darr;</button>
    </div>
    <div class="description">
      <div v-if="open">{{ text }}</div>
    </div>
  </div>
</template>

<style scoped lang=scss>

@import "./src/assets/main.scss";

</style>