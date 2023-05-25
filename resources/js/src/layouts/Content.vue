<template>
  <v-app>
    <nav-menu :is-drawer-open.sync="isDrawerOpen"></nav-menu>

    <v-app-bar
      app
      flat
      absolute
      color="transparent"
    >
      <div class="boxed-container w-full">
        <div class="d-flex align-center mx-6">
          <!-- Left Content -->
          <v-app-bar-nav-icon
            class="d-block d-lg-none me-2"
            @click="isDrawerOpen = !isDrawerOpen"
          ></v-app-bar-nav-icon>
          <v-text-field
            rounded
            dense
            outlined
            :prepend-inner-icon="icons.mdiMagnify"
            class="app-bar-search flex-grow-0"
            hide-details
          ></v-text-field>

          <v-spacer></v-spacer>

          <!-- Right Content -->
          <a
            href="https://github.com/charlie210012"
            target="_blank"
            rel="nofollow"
          >
            <v-icon class="ms-6 me-4">
              {{ icons.mdiGithub }}
            </v-icon>
          </a>
          <theme-switcher></theme-switcher>
          <v-btn
            icon
            small
            class="ms-3"
          >
            <v-icon>
              {{ icons.mdiBellOutline }}
            </v-icon>
          </v-btn>
          <app-bar-user-menu></app-bar-user-menu>
        </div>
      </div>
    </v-app-bar>

    <v-main>
      <div class="app-content-container boxed-container pa-6">
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
import { ref } from '@vue/composition-api'
import { mdiMagnify, mdiBellOutline, mdiGithub } from '@mdi/js'
import ThemeSwitcher from './components/ThemeSwitcher.vue'
import AppBarUserMenu from './components/AppBarUserMenu.vue'
import NavMenu from './components/vertical-nav-menu/NavMenu.vue'

export default {
  components: {
    ThemeSwitcher,
    AppBarUserMenu,
    NavMenu,
  },
  setup() {
    const isDrawerOpen = ref(null)

    return {
      isDrawerOpen,

      // Icons
      icons: {
        mdiMagnify,
        mdiBellOutline,
        mdiGithub,
      },
    }
  },
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
