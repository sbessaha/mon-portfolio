<template>
  <v-app id="home">
    <NavBar />
    <v-container fluid>
      <div class="head">
        <v-row>
          <v-col cols="5">
            <div style="position: relative" class="mt-10">
              <h1 class="text-grey">Bienvenue !</h1>
              <h1 class="text-white">Je suis Sofiane Bessaha</h1>
              <span class="text-grey">Developpeur fullstack et intégrateur web</span><br />
            </div>
          </v-col>
        </v-row>
      </div>

      <v-col cols="12" class="" id="about">
        <div>
          <v-row>
            <v-col cols="12" sm="6">
              <div class="egg">
                <v-img src="Sofiane.png" max-height="300" class=""></v-img>
              </div>
            </v-col>
            <v-col cols="12" sm="6">
              <h5 class="mt-16 mb-6">À propos de moi</h5>
              <h4 class="mt-n2">Je suis un développeur web fullstack</h4>
              <p class="text-grey-darken-2 mt-2">
                Fort de mon apprentissage a l'école Epitech, je suis capable de
                créer des applications web simple ou complexe. Je suis
                également capable de créer des applications mobiles et de
                m'occuper de projet back-end.<br>
                Grâce à mon alternance de 14mois au sein de Adeo Service en tant que Developpeur fullstack,
                j'ai acquis une certaine expérience pour travailler au sein d'une entreprise et avec un groupe sur
                un projet concret et utile.
              </p>
              <br />
              <v-btn tile dark color="yellow" class="mt-4" href="CV.jpeg" download>
                Télécharger mon CV
              </v-btn>
            </v-col>
          </v-row>
        </div>
      </v-col>
      <v-col cols="12" class="padd">
        <div class="first" id="project">
          <v-row>
            <v-col cols="12">
              <div class="child pb-2">
                <v-btn
                  icon="fas fa-laptop"
                  color="#FBDF7E"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-2">Site internet</h3>
                <p class="text-grey ml-3 mt-2 text-caption">
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
                <h3 class="ml-3 mt-2">Appli mobile</h3>
                <p class="text-grey ml-3 mt-2 text-caption">
                  Grâce â ma formation <br /> je peux egalement créer <br />
                  des applications mobiles fullstack.<br />
                </p>
              </div>
              <div class="child pb-4">
                <v-btn
                  icon="fas fa-camera"
                  color="#FBDF7E"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-2">Projet back-end</h3>
                <p class="text-grey ml-3 mt-2 text-caption">
                  Je peux également m'occuper<br />de projet uniquement
                  <br />back-end avec les technologies<br />les plus récentes.
                </p>
              </div>
            </v-col>
          </v-row>
          <v-divider id="portfolio"></v-divider>
        </div>
      </v-col>

      <v-col cols="12" sm="12">
        <div class="d-flex justify-center mb-6">
          <v-btn @click="setFilterCategory('all')" color="#FBDF7E" class="mr-2">Tout afficher</v-btn>
          <v-btn @click="setFilterCategory('frontend')" class="mr-2" variant="tonal">Front-end</v-btn>
          <v-btn @click="setFilterCategory('backend')" class="mr-2" variant="tonal">Back-end</v-btn>
          <v-btn @click="setFilterCategory('fullstack')" class="mr-2" variant="tonal">Full stack</v-btn>
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
        <v-container class="fill-height d-flex flex-column justify-center align-center text-center">
          <p class="text-h6 mb-4 mt-4">Pour voir d'autres projets, n'hésitez pas à visiter mon GitHub.</p>

          <v-btn
              href="https://github.com/sbessaha"
              target="_blank"
              variant="plain"
          >
            <v-img src="github.png" height="72" width="72" contain />
          </v-btn>

          <div class="mt-10"></div>
        </v-container>
      </v-col>

      <v-divider></v-divider>

      <div id="compétences"></div>

      <v-col cols="12" class="mt-8">
        <h2 class="text-center mb-8">
          Compétences Acquises <br> à la Web Académie
        </h2>
        <v-row>
          <template v-for="(skill, index) in skills" :key="index">
            <v-col cols="12" md="6" lg="4" class="text-center">
              <v-card class="pa-3 skill-card">
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
              <span class="text-caption">51 rue Roure, 59130 Lambersart</span
              ><br />
              <v-btn
                icon="fas fa-envelope"
                color=""
                class="mt-10"
                variant="outlined"
              ></v-btn
              ><br />
              <span class="text-caption">sofiane.bessaha@epitech.eu </span> <br />
              <v-btn
                  class="mt-10 mb-2"
                  href="https://www.linkedin.com/in/sofiane-bessaha-415127271/"
                  target="_blank"
                  variant="plain"
              >
                <v-img src="linkedin.png" height="48" width="48" contain />
              </v-btn>
              <br />
              <span class="text-caption">Sofiane Bessaha</span> <br />
            </div>
          </v-col>
          <v-col cols="12" sm="8">
            <h1 class="mt-8">Contactez-moi !</h1>
            <v-divider></v-divider>

            <v-row class="mt-10">
              <v-col cols="12" sm="6">
                <v-text-field
                    v-model="form.name"
                    label="Nom"
                    persistent-hint
                    variant="outlined"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-text-field
                    v-model="form.email"
                    label="Mail"
                    type="email"
                    persistent-hint
                    variant="outlined"
                ></v-text-field>
              </v-col>
            </v-row>

            <v-textarea
                v-model="form.message"
                label="Message"
                persistent-hint
                variant="outlined"
            ></v-textarea>

            <v-btn color="#FBDF7E" class="mt-2" @click="submitForm">Envoyer</v-btn>

            <p v-if="successMessage" class="text-green">{{ successMessage }}</p>
            <p v-if="errorMessage" class="text-red">{{ errorMessage }}</p>
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

const form = ref({
  name: "",
  email: "",
  message: "",
});

const successMessage = ref(null);
const errorMessage = ref(null);

const submitForm = async () => {
  successMessage.value = null;
  errorMessage.value = null;

  try {
    const response = await fetch("https://formspree.io/f/mblrryag", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        name: form.value.name || "",
        email: form.value.email || "",
        message: form.value.message || "",
      }),
    });

    if (response.ok) {
      successMessage.value = "Message envoyé avec succès !";
      form.value = { name: "", email: "", message: "" };
    } else {
      throw new Error("Erreur lors de l'envoi du message.");
    }
  } catch (error) {
    errorMessage.value = error.message;
  }
};


export default defineComponent({
  name: "HomeView",
  setup() {
    const slider2 = ref(50);
    const filterCategory = ref("all");
    const setFilterCategory = (category) => {
      if (category) {
        filterCategory.value = category;
      }
    }

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
        category: "backend",
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
        img: "CosMarket.png",
        title: "Ecommerce",
        description: "Site Ecommerce de vente en ligne de skin Counter Strike",
        techno: "Laravel, ReactJS, PHPMyAdmin",
        category: "fullstack",
      },
      {
        img: 'MYDEV.png',
        title: "MyDev",
        description: "Application pour collaborateur au sein de l'entreprise",
        techno: "Vue3, Vue2, PostgreSQL, Java spring boot",
        category: "fullstack"
      }
    ];

    const filteredItems = computed(() => {
      if (!items) return [];
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
          "Node.js, Express.js, PHP, PostgreSQL, Laravel, Java",
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
          "VScode, Pack JetBrains (IntelliJ IDEA, WebStorm, Datagrip)",
          "Test: Postman",
        ],
      },
      {
        title: "Autres Compétences",
        details: [
          "Photoshop, Figma, Gimp",
          "PowerPoint, Word, Excel, Trello, Jira",
          "Français, Anglais",
        ],
      },
    ];

    return {
      slider2,
      filterCategory,
      filteredItems,
      items,
      skills,
      form,
      setFilterCategory,
      submitForm,
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
  height: 350px;
}

.head:before,
.head:after {
  content: "";
  position: absolute;
  top: 0;
  height: 70%;
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

.skill-card {
  background-color: black !important;
  border: 2px solid #FBDF7E !important;
  color: white !important;
  transition: transform 0.3s ease-in-out;
}

.skill-card:hover {
  transform: scale(1.05);
}

</style>