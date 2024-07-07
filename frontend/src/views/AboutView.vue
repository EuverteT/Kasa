<script>
import json from '../assets/about.json';

export default{

data(){
    return {
        myJson: json,
        data: [],
    }
  },
methods: {
  closeText(data){
    document.getElementById(data.expandBtn).style.display = 'block'
    document.getElementById(data.name).style.display = 'none'
    document.getElementById(data.notExpandBtn).style.display = 'none'

  },
  openText(data){
    document.getElementById(data.expandBtn).style.display = 'none'
    document.getElementById(data.name).style.display = 'block'
    document.getElementById(data.notExpandBtn).style.display = 'block'
  }
}
}
</script>

<template>
  <div class="component"v-for="data of myJson">
    <div class="component-title">
        <div>{{ data.title }}</div>
        <button :id=data.notExpandBtn @click= "closeText(data)" class="notExpand-button" >&uarr;</button>
        <button style="display: none" :id=data.expandBtn @click= "openText(data)" class="expand-button">&darr;</button>
    </div>
    <div :id=data.name class="description">
      <div>{{ data.text }}</div>
    </div>
  </div>
</template>

<style scoped lang=scss>
@import "./src/assets/main.scss";

</style>
