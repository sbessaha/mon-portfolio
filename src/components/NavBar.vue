<template>
    <v-app-bar app color="black" dark flat class="px-12" >
  
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
  </style>