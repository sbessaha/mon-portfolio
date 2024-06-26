<template>
  <v-app id="home">
    <NavBar />
    <v-container fluid>
      <div class="head">
        <v-row>
          <v-col cols="5">
            <div style="position: relative" class="mt-16">
              <h1 class="text-grey">Bienvenue !</h1>
              <h1 class="text-white">Je suis Sofiane Bessaha</h1>
              <span class="text-grey">Developpeur fullstack et intégrateur web</span><br />
            </div>
          </v-col>

          <v-col cols="2">
            <div
              style="
                position: absolute;
                z-index: 9999;
                bottom: 0;
                margin-left: auto;
                margin-right: auto;
                left: 0;
                right: 0;
                text-align: center;
              "
              class="mt-16"
            >
            </div>
          </v-col>

          <v-col cols="5">
            <div style="position: relative; z-index: 9999" class="mt-16">
              <v-img src="" contain max-height="300"></v-img>
            </div>
          </v-col>
        </v-row>
      </div>

      <v-col cols="12" class="mt-16" id="about">
        <div>
          <v-row>
            <v-col cols="12" sm="6">
              <div class="egg">
                <v-img src="Sofiane.png" max-height="300" class=""></v-img>
              </div>
            </v-col>
            <v-col cols="12" sm="6">
              <h5 class="mt-16">A propos de moi</h5>
              <div style="width: 120px">
                <v-slider
                  v-model="slider2"
                  color="yellow"
                  label="track-color"
                ></v-slider>
              </div>
              <h4 class="mt-n4">Je suis un développeur web fullstack</h4>
              <p class="text-grey">
                Fort de mon apprentissage a l'école Epitech, je suis capable de
                créer des applications web simple ou complexe. Je suis
                également capable de créer des applications mobiles et de
                m'occuper de projet back-end.
              </p>
              <br />
              <v-btn tile dark color="yellow" class="mt-4" href="CV.pdf" download>
                Télécharger mon CV
              </v-btn>
            </v-col>
          </v-row>
        </div>
      </v-col>

      <div class="text-center mt-4">
        <h2>Ou j'en suis ?</h2>
        <div style="width: 120px; margin: 0 auto">
          <v-slider
            v-model="slider2"
            color="yellow"
            label="track-color"
          ></v-slider>
        </div>
      </div>
      <v-col cols="12" class="padd" id="portfolio">
        <div class="first" id="project">
          <v-row>
            <v-col cols="12">
              <div class="child">
                <v-btn
                  icon="fas fa-laptop"
                  color="#FBDF7E"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Site internet</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Je suis capable de créer des <br />applications web
                  simple ou <br />complexe en plusieurs
                  <br />technologies.
                </p>
              </div>
              <div class="child">
                <v-btn
                  icon="fas fa-mobile-alt"
                  color="#FBDF7E"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Appli mobile</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Grâce â ma formation <br /> je peux egalement créer <br />
                  des applications mobiles fullstack.<br />
                </p>
              </div>
              <div class="child">
                <v-btn
                  icon="fas fa-camera"
                  color="#FBDF7E"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Projet back-end</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Je peux également m'occuper<br />de projet uniquement
                  <br />back-end avec les technologies<br />les plus récentes.
                </p>
              </div>
            </v-col>
          </v-row>
          <v-divider></v-divider>
        </div>
      </v-col>

      <v-col cols="12" sm="12" id="services">
        <div class="d-flex justify-center mb-6">
          <v-btn @click="filterCategory = 'all'" color="#FBDF7E" class="mr-2">Tout afficher</v-btn>
          <v-btn @click="filterCategory = 'frontend'" class="mr-2" variant="tonal">Front-end</v-btn>
          <v-btn @click="filterCategory = 'backend'" class="mr-2" variant="tonal">Back-end</v-btn>
          <v-btn @click="filterCategory = 'fullstack'" class="mr-2" variant="tonal">Full stack</v-btn>
        </div>
      </v-col>

      <v-col cols="12" class="imgHover">
        <v-row class="fill-height" align="center" justify="center">
          <template v-for="(item, i) in filteredItems" :key="i">
            <v-col cols="12" md="4">
              <v-hover v-slot="{ isHovering, props }">
                <v-card
                  :elevation="isHovering ? 12 : 2"
                  :class="{ 'on-hover': isHovering }"
                  v-bind="props"
                >
                  <v-img :src="item.img" height="225px" cover> </v-img>
                  <v-card-title>{{ item.title }}</v-card-title>
                  <v-card-subtitle>{{ item.description }}</v-card-subtitle>
                  <v-card-subtitle>{{ item.techno }}</v-card-subtitle>
                </v-card>
              </v-hover>
            </v-col>
          </template>
        </v-row>
      </v-col>

      <v-col cols="12" class="mt-16" id="compétences">
        <h2 class="text-center mb-8">Compétences Acquises <br> à la Web Académie</h2>
        <v-row>
          <template v-for="(skill, index) in skills" :key="index">
            <v-col cols="12" md="6" lg="4" class="text-center">
              <v-card class="pa-3">
                <v-card-title class="justify-center">{{ skill.title }}</v-card-title>
                <v-card-text>
                  <v-list dense>
                    <v-list-item v-for="(detail, i) in skill.details" :key="i">
                      <v-list-item-content>
                        <v-list-item-title>{{ detail }}</v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-list>
                </v-card-text>
              </v-card>
            </v-col>
          </template>
        </v-row>
      </v-col>

      <v-col cols="12" sm="12" class="px-16" id="contact">
        <v-row>
          <v-col cols="12" sm="4">
            <div class="child">
              <h1>Contact</h1>
              <v-btn
                icon="fas fa-map-marker-alt"
                color=""
                class="mt-10"
                variant="outlined"
              ></v-btn
              ><br />
              <span class="text-caption">57 rue Bonte Pollet, 59000 Lille </span
              ><br />
              <v-btn
                icon="fas fa-phone-alt"
                color=""
                class="mt-10"
                variant="outlined"
              ></v-btn
              ><br />
              <span class="text-caption">07 82 02 86 01</span> <br />
              <v-btn
                icon="fas fa-envelope"
                color=""
                class="mt-10"
                variant="outlined"
              ></v-btn
              ><br />
              <span class="text-caption">sofiane.bessaha@epitech.eu </span> <br />
            </div>
          </v-col>
          <v-col cols="12" sm="8">
            <h1 class="mt-8">Envoyez moi un message !</h1>
            <v-divider></v-divider>
            <span class="text-caption"
              >N'hésitez pas a m'envoyer un message pour me contacter,
            que ça soit via ce formulaire ou via les différentes informations,
            personnels qui sont mis à votre disposition.</span
            >
            <v-row class="mt-10">
              <v-col cols="12" sm="6">
                <v-text-field
                  label="Nom"
                  persistent-hint
                  variant="outlined"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-text-field
                  label="Téléphone"
                  persistent-hint
                  variant="outlined"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-textarea
              label="Message"
              persistent-hint
              variant="outlined"
            ></v-textarea>
            <v-btn color="#FBDF7E" class="mt-2">Envoyez</v-btn>
          </v-col>
        </v-row>
      </v-col>

    </v-container>
    <FooterView />
  </v-app>
</template>

<script>
import { defineComponent, ref, computed } from "vue";
import NavBar from "../components/NavBar.vue";
import FooterView from "../components/FooterView.vue";

export default defineComponent({
  name: "HomeView",
  setup() {
    const slider2 = ref(50);
    const filterCategory = ref("all");
    const items = [
      {
        img: "Twitter_1.png",
        title: "My_Twitter",
        description: "Projet de clone de Twitter",
        techno: "PHP, JS, MySQL, HTML, TailwindCSS, PHPMyAdmin",
        category: "fullstack",
      },
      {
        img: "FreeAds.png",
        title: "FreeAds",
        description: "Plateforme de petites annonces en ligne",
        techno: "Laravel, HTML, TailwindCSS, PHPMyAdmin",
        category: "fullstack",
      },
      {
        img: "Goodrenov.png",
        title: "Good Renov",
        description: "Site web pour une entreprise de rénovation",
        techno: "HTML, JS, TailwindCSS, Formspree",
        category: "frontend",
      },
      {
        img: "Spotify.png",
        title: "Spotifine",
        description: "Application musicale inspirée de Spotify",
        techno: "React, API Externe",
        category: "frontend",
      },
      {
        img: "cinema.png",
        title: "My_Cinema",
        description: "Application de gestion de cinéma",
        techno: "PHP, MySQL, HTML, CSS, PHPMyAdmin",
        category: "backend",
      },
    ];

    const filteredItems = computed(() => {
      if (filterCategory.value === "all") {
        return items;
      }
      return items.filter(item => item.category === filterCategory.value);
    });

    const skills = [
      {
        title: "Développement Frontend",
        details: [
          "HTML, TailwindCSS, JavaScript",
          "Frameworks: Vue.js, React",
          "Design Responsive",
        ],
      },
      {
        title: "Développement Backend",
        details: [
          "Node.js, Express.js, PHP, MySQL, Laravel, Symfony",
          "Bases de données: MongoDB, PHPMyAdmin",
          "Utilisation d'une API externe",
        ],
      },
      {
        title: "Soft Skills",
        details: [
          "Travail en équipe",
          "Gestion du temps",
          "Rigueur, autonomie",
        ],
      },
      {
        title: "Développement Mobile",
        details: [
          "React Native",
          "Expo",
          "Applications hybrides",
        ],
      },
      {
        title: "Outils et Technologies",
        details: [
          "Git, GitHub, GitKraken",
          "VScode, IntelliJ IDEA",
          "Test: Postman",
        ],
      },
      {
        title: "Autres Compétences",
        details: [
          "Design: Photoshop, Figma",
          "PowerPoint, Word, Excel, Trello",
          "Langues: Français, Anglais",
        ],
      },
    ];

    return {
      slider2,
      filterCategory,
      filteredItems,
      items,
      skills,
    };
  },
  components: {
    NavBar,
    FooterView,
  },
});
</script>

<style scoped>
.v-container {
  padding: 16px 0;
}

.head {
  position: relative;
  text-align: center;
  padding: 12px;
  margin-bottom: 6px;
  height: 400px;
  width: 100%;
  color: white;
}

.head:before,
.head:after {
  content: "";
  position: absolute;
  top: 0;
  height: 100%;
  width: 50%;
  background: black;
  transform: skew(0deg, 6deg);
}

.head:before {
  left: 0;
}

.head:after {
  right: 0;
  transform: skew(0deg, -6deg);
}

.egg {
  display: block;
  margin-left: 100px;
  margin-top: 50px;
  width: 356px;
  height: 300px;
  background-color: #fbdf7e;
  border-radius: 50% / 60%;
}

.first {
  width: 100%;
  height: 280px;
  text-align: center;
  padding: 2rem;
}

.child {
  display: inline-block;
  padding: 2rem 1rem;
  vertical-align: middle;
  text-align: center;
  margin-right: 8px;
}

.imgHover {
  padding: 0 200px;
}

.hover-card {
  position: relative;
  overflow: hidden;
}

.overlay-content {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 16px;
}
</style>