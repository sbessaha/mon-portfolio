<template>
  <v-app-bar color="black" dark flat class="px-4 px-md-16">
    <v-toolbar-title class="text-white">Sofiane Bessaha</v-toolbar-title>
    <v-spacer class="d-none d-md-flex"></v-spacer>
    
    <div class="d-none d-md-flex">
      <v-btn text @click="scroll('home')">Accueil</v-btn>
      <v-btn text @click="scroll('about')">À propos</v-btn>
      <v-btn text @click="scroll('portfolio')">Portfolio</v-btn>
      <v-btn text @click="scroll('compétences')">Compétences</v-btn>
      <v-btn text @click="scroll('contact')">Contact</v-btn>
    </div>

    <v-app-bar-nav-icon
      class="d-md-none"
      @click.stop="drawer = !drawer"
    ></v-app-bar-nav-icon>
  </v-app-bar>

  <v-navigation-drawer
    v-model="drawer"
    temporary
    location="left"
    color="black"
  >
    <v-list>
      <v-list-item @click="scrollTo('home')">
        <v-list-item-title>Accueil</v-list-item-title>
      </v-list-item>
      <v-list-item @click="scrollTo('about')">
        <v-list-item-title>À propos</v-list-item-title>
      </v-list-item>
      <v-list-item @click="scrollTo('portfolio')">
        <v-list-item-title>Portfolio</v-list-item-title>
      </v-list-item>
      <v-list-item @click="scrollTo('compétences')">
        <v-list-item-title>Compétences</v-list-item-title>
      </v-list-item>
      <v-list-item @click="scrollTo('contact')">
        <v-list-item-title>Contact</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
    };
  },
  methods: {
    scroll(refName) {
      const element = document.getElementById(refName);
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
    scrollTo(refName) {
      this.scroll(refName);
      this.drawer = false;
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