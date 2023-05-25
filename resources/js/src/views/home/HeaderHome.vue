<template>
  <v-app-bar app dark color="black">
    <v-toolbar-title>
      <div class="image-container">
        <img class="logo-image" src="/images/logos/logo-parabarberos.png" alt="Logo" />
      </div>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items>
      <v-btn text>Home</v-btn>
      <v-btn text>About</v-btn>
      <v-btn text>Contact</v-btn>
      <v-btn text>Home</v-btn>
      <v-btn text>About</v-btn>
      <v-btn text>Contact</v-btn>
    </v-toolbar-items>
  </v-app-bar>
</template>
<script>
export default {
  name: 'HeaderHome'
}
</script>

<style>
.image-container {
  display: flex;
  justify-content: left;
  align-items: center;
}

.logo-image {
  max-width: 10%;
  max-height: 20%;
}
</style>
