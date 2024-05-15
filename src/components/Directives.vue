<script setup>
import { ref } from "vue" 
let msg = ref("Soy un tooltip")
let checked = ref(false);

let data =["Hola", "mundo", "cruel"];
// let filtered = data.filter((word) => word.includes('o'));


let filtered = data.filter(function (word){
    return word.includes('o')
}
)


</script>

<template>
    <input 
    class="border"
    :class="{'border-red-500':checked}" 
    v-model="msg"/>
    <div :title="msg">
        {{ msg }}   
    </div>
    <label for="check">seleccionado {{ checked }}</label>
    <input type="checkbox" v-model="checked"/>

    <ul>
        <li v-for="(text, index) in filtered" :key="index">
            {{ text }}
        </li>
       
    </ul>


</template>