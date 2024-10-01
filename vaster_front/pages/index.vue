<template>

      <div>
        <VFileInput v-model="files" label="Selectionner fichier"></VFileInput>
      </div>
      <div>
        Hello World!
        {{ files.values }}
      </div>
      <!-- <v-btn color="success" @click="goFunc">Go!</v-btn> -->

      <v-select v-model="selected_cols" :items="colonnes" label="Favorite Fruits" multiple>
        <template v-slot:prepend-item>
          <v-list-item ripple @mousedown.prevent @click="toggle">
            <v-list-item-action>
              <v-icon :color="selected_cols.length > 0 ? 'indigo darken-4' : ''"></v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>
                Selectionner tous
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider class="mt-2"></v-divider>
        </template>
      </v-select>
      <v-btn color="success" @click="post_ACP">ACP!</v-btn>
</template>

<script setup lang="ts">
import * as PaPa from 'papaparse';

const runtimeConfig = useRuntimeConfig()
console.log(runtimeConfig.apiSecret)
const files = ref([]);
let colonnes = ref([""]);
let data_csv: any[] = [];
var filename = "";
let selected_cols = ref([""]);
watch(files, goFunc);

function toggle() {
  if (selected_cols.value.length == colonnes.value.length) {
    selected_cols.value = []
  } else {
    selected_cols.value = colonnes.value.slice()
  }
}

function goFunc() {
  console.log("file");
  console.log("file", files);

  const csv_file = files.value[0];
  console.log("file", csv_file);
  let reader = new FileReader();
  reader.readAsText(csv_file);
  reader.onload = () => {
    const csv_string: string = reader.result as string;
    console.log("brrr", csv_string);
    const parser = PaPa.parse(csv_string, { delimiter: ";" });
    data = PaPa.parse(csv_string, { delimiter: ";", header: true }).data;
    console.log(parser.data[0]);
    colonnes.value = parser.data[0] as [string];
  }
}


async function post_ACP() {
  console.log("ACP !!!", data_csv[0]);
  let dictionary = data_csv.map(row => { return Object.fromEntries(Object.entries(row).filter(([k, v]) => Object.values(selected_cols.value).includes(k))) });
  console.log(dictionary);
  const { res } = await useFetch('http://localhost:4200', {
    method: 'POST',
    body: dictionary,
  });
  console.log(data)
}

</script>
