<script setup lang="ts">
    /*********************************************************
    prog name: 關於經貿營, author: 薛潔, date: 2022/07/30
    Todo: 
    **********************************************************/	
    import { ref, onMounted } from "vue"
    import { useFetch } from "@vueuse/core"
    import liwaData from "../static/aboutSIED.json"

    const parag1 = ref('')
    const parag2 = ref('')

    onMounted(() => {
        parag1.value = liwaData[0].parag1
        parag2.value = liwaData[0].parag2
    })

    definePageMeta({
      title: 'SIED介紹',
    })    
</script>

<template>
<div class="w-full h-full lg:w-[1024px] lg:mx-auto">
    <div class="w-full h-full bg-slate-100 px-4">
        <h1 class="text-3xl font-bold text-left mb-4 pt-8">SIED介紹</h1>
        <h2 class="text-md font-semibold my-2">什麼是SIED?</h2>
        <p v-html="parag1"></p>
        <h3 class="text-md font-semibold my-2">SIED特色</h3>
        <p v-html="parag2"></p>
        <div class="w-64 h-48 flex">
            <img src="https://img.onl/OIeK4S" /> 
            <img src="https://img.onl/QDNM16" />
         </div>
    </div>
 </div>   
</template>