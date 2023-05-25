<template>
  <v-app>

    <v-main>
      <div class="app-content-container boxed-container pa-8">
        <slot></slot>
      </div>
    </v-main>
    <v-footer
      app
      inset
      color="transparent"
      absolute
      height="56"
      class="px-0"
    >
      <div class="boxed-container w-full">
        <div class="mx-6 d-flex justify-space-between">
          <span>
            &copy; 2023 <a
              href="#"
              class="text-decoration-none"
              target="_blank"
            >Parabarberos</a></span>
          <span class="d-sm-inline d-none">
            <a
              href="https://sidevtech.com"
              target="_blank"
              class="me-6 text--secondary text-decoration-none"
            >Desarrollado por Sidevtech</a>
            <a
              href="#"
              target="_blank"
              class="me-6 text--secondary text-decoration-none"
            >Nit: 900939232 - 8</a>
            <a
              href="#"
              target="_blank"
              class="text--secondary text-decoration-none"
            >MIT Licence</a>
          </span>
        </div>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.v-app-bar ::v-deep {
  .v-toolbar__content {
    padding: 0;

    .app-bar-search {
      .v-input__slot {
        padding-left: 18px;
      }
    }
  }
}

.boxed-container {
  max-width: 1440px;
  margin-left: auto;
  margin-right: auto;
}
</style>

