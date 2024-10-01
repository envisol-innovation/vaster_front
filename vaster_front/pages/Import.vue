<template>
  
    <v-layout class="rounded rounded-md">
      
      <v-main >
        <v-file-input accept=".PNG" label="File input"></v-file-input>
        <v-img :width="300" aspect-ratio="16/9" cover src=""></v-img>
        <div>

        </div>
      </v-main>

    </v-layout>
  </template>

  <script setup lang='ts'>
    const runtimeConfig = useRuntimeConfig()
    console.log(runtimeConfig.apiSecret)
    const files = ref([]);

    

  </script>
  
