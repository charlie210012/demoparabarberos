<template>
  <div>
    <v-carousel>
      <v-carousel-item v-for="(item, index) in carouselItems" :key="index">
        <v-img :src="item.image" :alt="item.caption"></v-img>
        <template #overlay>
          <v-sheet class="overlay">
            <span class="caption">{{ item.caption }}</span>
          </v-sheet>
        </template>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
export default {
  name: 'StoreCarousel',
  data() {
    return {
      carouselItems: [
        { image: '/images/pages/card-basic-boat.png', caption: 'Caption 1' },
        { image: '/images/pages/card-basic-mobile.png', caption: 'Caption 2' },
        { image: '/images/pages/card-basic-influencer.png', caption: 'Caption 3' },
      ]
    };
  }
}
</script>

<style>
</style>
