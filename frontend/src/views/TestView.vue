<script>
import HeureCourante from '../components/HeureCourante.vue';
import json from '../assets/logements.json';

export default{
    data(){
        return {
            myJson: json
        }
    }
}

</script>

<template>
    <main>
        <div>CECI EST UN TEXTE EN HTML</div>
        <HeureCourante />
        <div v-for="data in myJson">{{ data }}</div>
    </main>
</template>