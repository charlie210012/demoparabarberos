<template>
  <v-app-bar app dark color="black">
    <v-toolbar-title class="image-container">
        <img class="logo-image" src="/images/logos/logo-parabarberos.png" alt="Logo" />
    </v-toolbar-title>
    <v-toolbar-items>
      <v-text-field
          v-model="searchText"
          label="Buscar"
          solo-inverted
          clearable
          append-icon="mdi-magnify"
          @keyup.enter="performSearch"
          class="wider-search"
        ></v-text-field>
    </v-toolbar-items>
    <v-menu
      v-if="$vuetify.breakpoint.smAndDown"
      offset-y
    >
      <template v-slot:activator="{ on }">
        <v-btn icon v-on="on">
          <v-icon>{{ icon.mdiMenu }}</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item v-for="(item, index) in menuItems" :key="index" link>
          <v-list-item-title>{{ item }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    <v-toolbar-items
      v-else
      class="menu-items"
    >
      <v-btn text color="white" v-for="(item, index) in menuItems" :key="index">{{ item }}</v-btn>
    </v-toolbar-items>
    <v-toolbar-items class="cart-icon">
      <v-btn icon color="white" @click="openModal">
        <v-icon>{{ icon.mdiAccount }}</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn icon color="white" @click="openCartModal">
        <v-icon>{{ icon.mdiCart }}</v-icon>
      </v-btn>
    </v-toolbar-items>
  </v-app-bar>
</template>

<script>
import { ref } from '@vue/composition-api'
import {
  mdiMenu,
  mdiCart,
  mdiAccount,
} from '@mdi/js'
export default {
  name: 'HeaderHome',
  data() {
    return {
      menuItems: ['Inicio', 'Tienda','Mayorista','Contactos']
    }
  },
  setup() {
    return {
      icon: {
        mdiMenu,
        mdiCart,
        mdiAccount,
      }
    };
  }
}
</script>

<style scoped>
.image-container {
  display: flex;
  align-items: center;
}

.logo-image {
  max-width: 100%;
  max-height: 100%;
  width: 30%;
  height: 30%;
  justify-content: left;
}

.menu {
  margin-top: 20%;
}

.cart-icon {
  display: flex;
  align-items: center;
  margin-right: 10px;
}

.menu-items {
  display: flex;
  align-items: flex-start;
  margin-top: 2.4%;
}

.search-component {
  margin: 20px;
}

@media (max-width: 600px) {
  .search-component v-col {
    width: 100%;
  }
  .logo-image {
    max-width: 100%;
    max-height: 100%;
    width: 60%;
    height: 60%;
    justify-content: left;
  }
}

.wider-search {
  width: 600px;/* Ajusta el ancho según tus necesidades */
  margin-top: 1%;
  margin-right: 20%;
}

@media (max-width: 600px) {
  .wider-search {
    width: 200px; /* Hace que el campo de búsqueda ocupe todo el ancho en dispositivos móviles */
  }
}
</style>
