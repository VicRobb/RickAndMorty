<template>
    <div>Home</div>
    {{ character }}
</template>

<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

onMounted(() => {
    getCharacter();
})

const character = ref(null)

const getCharacter = async() => {
    await axios.get('https://rickandmortyapi.com/api/character')
        .then((resolve) => {
            console.log(resolve.data.results);
            character.value = resolve.data.results
        }).catch((error) => {
            console.log(error);
        })
}

</script>

<style>
</style>