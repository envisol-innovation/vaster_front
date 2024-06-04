<template>
    <NuxtLayout>
      <v-app>
        <div>
            <VFileInput v-model="files" label="Selectionner fichier" ></VFileInput>
        </div>
        <div>
            Hello World!
            {{ files.values }}
        </div>
        <v-btn color="success" @click="goFunc(files)">Go!</v-btn>
      </v-app>
    </NuxtLayout>
</template>

<script setup lang="ts">
const runtimeConfig = useRuntimeConfig()
console.log(runtimeConfig.apiSecret)
const files = ref([File])
var filename = ""
// watch(file, )
function goFunc(files:any){
    console.log("file");
    console.log("file", files.value)
}

</script>
