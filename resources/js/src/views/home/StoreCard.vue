<template>
  <div>
    <v-row>
      <v-col v-for="i in 10" lg="4" sm="6" cols="12" class="align-self-start" :key="i">
          <v-card>
            <v-img :src="require('@/assets/images/pages/card-basic-brown-watch.jpg')"></v-img>
            <v-card-title>Apple Watch</v-card-title>
            <v-card-text>
              <p class="text--primary text-base">$249.40</p>
              3.1GHz 6-core 10th-generation Intel Core i5 processor, Turbo Boost up to 4.5GHz
            </v-card-text>
            <v-card-actions class="primary pa-0">
              <v-btn color="primary" block dark large> Add to cart </v-btn>
            </v-card-actions>
          </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'
import {
  mdiChevronUp,
  mdiChevronDown,
  mdiCartPlus,
  mdiShareVariantOutline,
  mdiLockOpenOutline,
  mdiStarOutline,
  mdiAccountOutline,
  mdiTrendingUp,
  mdiHelpCircleOutline,
} from '@mdi/js'


export default {
  data(){
    return {
      cardImage: require('/images/pages/card-basic-influencer.png'),
    };
  },
  setup() {
    const isCardDetailsVisible = false
    const rating = ref(5)

    return {
      isCardDetailsVisible,
      rating,

      // icons
      icons: {
        mdiChevronUp,
        mdiChevronDown,
        mdiCartPlus,
        mdiShareVariantOutline,
        mdiLockOpenOutline,
        mdiStarOutline,
        mdiAccountOutline,
        mdiTrendingUp,
        mdiHelpCircleOutline,
      },
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@resources/sass//preset/mixins.scss';

.avatar-center {
  top: -2rem;
  left: 1rem;
  border: 3px solid white;
  position: absolute;
}

// membership pricing
@include theme--child(memberpricing-bg) using ($material) {
  background-color: rgba(map-deep-get($material, 'primary-shade'), map-deep-get($material, 'states', 'hover'));
}

.memberpricing-bg {
  position: relative;
}
.membership-pricing {
  text-align: center;
  sup {
    font-size: 3.75rem;
    top: 9px;
  }
}
</style>
