<template>
  <h1> Calculatrice non fonctionnelle </h1>
  <div>
    <row>
      <v-btn color="succes" v-on:click="increment" width="50">+</v-btn>
      {{count}}      
      <v-btn @click="decrement" width="50">-</v-btn>
    </row>
  </div>


  <div>
    <row>
      <v-btn v-model="myText" id="1" v-on:click="setValeur1" width="50">1</v-btn>
      <v-btn v-model="myText" id="2" v-on:click="setValeur2" width="50">2</v-btn>
      <v-btn v-model="myText" id="3" v-on:click="setValeur3" width="50">3</v-btn>
      <v-btn v-model="myText" id="+" v-on:click="setValeurP" width="50">+</v-btn>
    </row>
  </div>

  <div>
    <row>
      <v-btn v-model="myText" id="4" v-on:click="setValeur4" width="50">4</v-btn>
      <v-btn v-model="myText" id="5" v-on:click="setValeur5" width="50">5</v-btn>
      <v-btn v-model="myText" id="6" v-on:click="setValeur6" width="50">6</v-btn>
      <v-btn v-model="myText" id="-" v-on:click="setValeurM" width="50">-</v-btn>
    </row>
  </div>

  <div>
    <row>
      <v-btn v-model="myText" id="7" v-on:click="setValeur7" width="50">7</v-btn>
      <v-btn v-model="myText" id="8" v-on:click="setValeur8" width="50">8</v-btn>
      <v-btn v-model="myText" id="9" v-on:click="setValeur9" width="50">9</v-btn>
      <v-btn v-model="myText" id="*" v-on:click="setValeurF" width="50">*</v-btn>
    </row>
  </div>

  <div>
    <row>
      <v-btn v-model="myText" id="0" v-on:click="reinitialise" width="193">Reinitialise</v-btn>
      <v-btn v-model="myText" id="0" v-on:click="egal" width="50">=</v-btn>
    </row>
  </div>

  <div>
    <p>value: {{ myText }}</p>
  </div>


</template>


<script setup lang="ts">
let count= ref(0);
var myText= ref("");
var resultat= 0;



function increment() {
  count.value += 1;  
}

function decrement() {
  count.value--;
}

function setValeur1() {
  myText.value += "1";
}

function setValeur2() {
  myText.value += "2";
}

function setValeur3() {
  myText.value += "3";
}

function setValeur4() {
  myText.value += "4";
}

function setValeur5() {
  myText.value += "5";
}

function setValeur6() {
  myText.value += "6";
}

function setValeur7() {
  myText.value += "7";
}

function setValeur8() {
  myText.value += "8";
}

function setValeur9() {
  myText.value += "9";
}

function setValeurP() {
  myText.value += "+";
}

function setValeurM() {
  myText.value += "-";
}

function setValeurF() {
  myText.value += "*";
}

function reinitialise() {
  myText.value = "";
}

function egal() {

  let taille= 0;
  let chaine= [""];
  let chaineF = [""];

  taille = myText.value.length;
  console.log (taille)

  for (let i = 0 ; i < taille; i++) {
    if (Number.isNaN(Number(myText.value[i]))){
      chaine = myText.value.split(myText.value[i])
      chaineF.push(myText.value[i-1])
      console.log (chaine)
      console.log (chaineF)
    }
  }

}
</script>