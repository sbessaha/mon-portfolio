<template>
    <v-app-bar color="black" dark flat class="px-16" >

      <v-spacer></v-spacer>
      <v-btn text @click="scroll('home')">Accueil</v-btn>
      <v-btn text @click="scroll('about')"  >À propos</v-btn>
      <v-btn text @click="scroll('portfolio')"  >Portfolio</v-btn>
      <v-btn text @click="scroll('compétences')"  >Compétences</v-btn>
      <v-btn text @click="scroll('contact')"  >Contact</v-btn>
    </v-app-bar>
  </template>

  <script>
  export default {
    methods: {
      scroll(refName) {
        const element = document.getElementById(refName);
        element.scrollIntoView({ behavior: "smooth" });
      },
    },
  };
  </script>

  <style>
  .v-app-bar {
    position: fixed !important;
    top: 0;
    width: 100%;
    z-index: 1000;
  }
  </style>