<template>
  <div >
    <header-home></header-home>
    <store-carousel></store-carousel>
    <v-spacer></v-spacer>
    <v-col cols="12"></v-col>
    <p class="text-2xl mb-6">
      Productos recientes
    </p>

    <store-card></store-card>

    <p class="text-2xl mt-14 mb-6">
      Navigation Cards
    </p>

    <card-navigation></card-navigation>

    <p class="text-2xl mt-14 mb-6">
      Solid Cards
    </p>

    <card-solid></card-solid>
    <button-whatsapp></button-whatsapp>
  </div>
</template>

<script>
import CardBasic from '../cards/CardBasic.vue'
import CardNavigation from '../cards/CardNavigation.vue'
import CardSolid from '../cards/CardSolid.vue'
import HeaderHome from './HeaderHome.vue'
import StoreCarousel from './StoreCarousel.vue'
import StoreCard from './StoreCard.vue'
import ButtonWhatsapp from './ButtonWhatsapp.vue'

export default {
  components: {
    CardBasic,
    CardNavigation,
    CardSolid,
    HeaderHome,
    StoreCarousel,
    StoreCard,
    ButtonWhatsapp,
  },
}
</script>
