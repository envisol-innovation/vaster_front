<template>
    <v-layout class="rounded rounded-md">
        <v-app-bar :elevation="2">
            <template v-slot:prepend>
                <v-app-bar-nav-icon></v-app-bar-nav-icon>
            </template>
            <v-app-bar-title>Import</v-app-bar-title>
        </v-app-bar>

      <v-navigation-drawer>
        <v-list>
          <v-list-item>
            <li><v-btn flat href="http://localhost:3000">
              <span> Home </span>
            </v-btn>
            </li>
  
            <li><v-btn flat href="http://localhost:3000/Calcul/Sondages">
              <span> Sondages </span>
            </v-btn>
            </li>
  
            <li><v-btn flat href="http://localhost:3000/Import">
              <span> Import </span>
            </v-btn>
            </li>

            <li><v-btn flat href="http://localhost:3000/Calcul/Calculatrice">
              <span> Calculatrice </span>
            </v-btn>
            </li>

          </v-list-item>
        </v-list>
      </v-navigation-drawer>
  
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
  
