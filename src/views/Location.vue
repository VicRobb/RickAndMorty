<template>
<div>Location</div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

onMounted(() => {
    getCharacter();

})

const getCharacter = async() => {
    await axios.get('https://rickandmortyapi.com/api/character')
        .then((resolve) => {
            console.log(resolve);
        }).catch((error) => {
            console.log(error);
        })
}


</script>

<style>
</style>