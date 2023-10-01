<template>
    <div  class="contenedor">
        <section  style="padding-bottom: 1rem; padding-top:1rem ; display: block; text-align: center; margin: 1rem; color :green; border: solid green 2px;" v-for="value in character" >
    
            <div class="contendor_hijo">
                <img v-bind:src="value.image" alt="" width="150" height="150" >
            
                <div style="padding-top: 1.5rem;">    
                    {{ value.name }}
                </div>
    
                <div style="padding-top: 1rem;">
                    {{value.type }}
                
                </div>
            </div>
        </section>
    </div>
    
    </template>
    
    <script setup>
    
    import { ref, onMounted } from 'vue'
    import axios from 'axios'
    
    onMounted(() => {
        getCharacter(); 
    })
    
    const character= ref(null);
    
    const getCharacter= async()=>{
        await axios.get('https://rickandmortyapi.com/api/character')
    
        .then((resolve)=> {
            character.value=resolve.data.results
        }).catch((error)=>{
            console.log(error);
        })
    
    }
    
    </script>
    
    <style scoped>
    
    .contenedor{
        
        display: grid;
        grid-template-columns: 25% 25% 25% 25%;
        align-items: center;
        
    }
    .contenedor_hijo{
        padding: 10px;
        width: 70%;
    }
    
 
    
    </style>