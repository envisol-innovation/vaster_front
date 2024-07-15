<template>
  <v-app>
    <v-app-bar :elevation="2">
      <v-app-bar-title>Envisol</v-app-bar-title>
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

          <li><v-btn flat href="http://localhost:3000/Calcul/Calculatrice">
              <span> Calculatrice </span>
            </v-btn>
          </li>

          </li>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <NuxtPage />
    </v-main>
  </v-app>
</template>
