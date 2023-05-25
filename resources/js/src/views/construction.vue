<template>
  <v-container class="text-center">
    <v-row align="center" justify="center">
      <v-col cols="12">
        <h1 class="headline">Página en construcción</h1>
        <v-img
          src="/images/barber-construction.svg"
          alt="Imagen de construcción"
          width="300"
          height="300"
          class="img mt-6"
        ></v-img>
        <p class="subheading mt-4">Estamos trabajando en mejorar nuestro sitio web.</p>
        <p class="subheading">Por favor, disculpe las molestias.</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'UnderConstruction',
};
</script>

<style scoped>
.headline {
  font-size: 36px;
  font-weight: bold;
}

.img {
  margin-left: 350px;
}

.subheading {
  font-size: 18px;
}
</style>
