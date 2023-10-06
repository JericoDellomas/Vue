<script setup>
import {ref} from 'vue' 

const input = ref('')
</script>
<template>
    <select v-model="input">
        <option value="html">HTML</option>
        <option value="css">CSS</option>
    </select>
    <p> p:{{ input }}</p>

    <!-- Conditional--> 
    <p v-if="input == 'html'"> Hypertext Markup Language</p>
    <p v-else-if="input == 'css'"> Cascading Style Sheets</p>
</template>