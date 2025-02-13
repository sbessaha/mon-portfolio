<template>
  <v-footer>
    <v-card
      elevation="0"
      rounded="0"
      width="100%"
      class="bg-grey text-center"
    >
      <v-card-text>
        <v-btn
          class="mx-4"
          href="https://www.linkedin.com/in/sofiane-bessaha-415127271/"
          target="_blank"
          variant="plain"
          color="white"
        >
          <v-img
            src="linkedin.png"
            alt="Twitter"
            height="32"
            width="32"
          ></v-img>
        </v-btn>
        <v-btn
          class="mx-4"
          href="https://github.com/sbessaha"
          target="_blank"
          variant="plain"
          color="white"
        >
          <v-img
            src="github.png"
            alt="GitHub"
            height="32"
            width="32"
          ></v-img>
        </v-btn>
      </v-card-text>

      <v-card-text class="text-white">
        @ {{ new Date().getFullYear() }} —
        <strong>Sofiane Bessaha</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>


<script>
export default {

}
</script>

<style>
.v-footer {
  padding: 8px 0 !important;
}
</style>