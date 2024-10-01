<template>
    <v-container>
        <v-navigation-drawer></v-navigation-drawer>
        <h1>déposer le fichier des données</h1>
        <v-file-input chips v-model="files"></v-file-input>
        <v-text-field v-model="test"> Test</v-text-field>
        <template v-if="files.length != 0">
            <v-btn>pleins </v-btn>
            <div>{{ files[0].name }} </div>
        </template>

    </v-container>
</template>

<script setup>
import { VInput } from 'vuetify/components';

var test= ref()
watch(test, (new_test) => {
    console.log("heya?", new_test);
})


const files = ref([])
watch(files, async (newFiles)=> {
    console.log("heya");
    console.log(newFiles.length, newFiles[0].name);
    

})
</script>