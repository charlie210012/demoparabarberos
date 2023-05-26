<template>
  <v-btn
    v-if="showButton"
    :class="{ 'whatsapp-fab-desktop': isDesktop, 'whatsapp-fab-mobile': isMobile }"
    color="green"
    dark
    fixed
    :bottom="isDesktop ? bottomOffsetDesktop : bottomOffsetMobile"
    :right="isDesktop ? rightOffsetDesktop : rightOffsetMobile"
    fab
    large
    @click="openWhatsApp"
  >
    <v-icon
    >{{ icons.mdiWhatsapp }}</v-icon>
  </v-btn>
</template>

<script>
import { mdiWhatsapp } from '@mdi/js';
export default {
  name: 'FloatingButtonWhatsApp',
  data() {
    return {
      showButton: true,
      phoneNumber: '+1234567890', // Reemplaza con tu número de teléfono de WhatsApp
      isDesktop: false,
      isMobile: false,
      bottomOffsetDesktop: 20,
      bottomOffsetMobile: 80,
      rightOffsetDesktop: 20,
      rightOffsetMobile: 20,
      icons: {
        mdiWhatsapp
      }
    };
  },
  mounted() {
    this.setDeviceType();
    window.addEventListener('resize', this.setDeviceType);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.setDeviceType);
  },
  methods: {
    setDeviceType() {
      this.isDesktop = window.innerWidth >= 1024;
      this.isMobile = window.innerWidth < 1024;
    },
    openWhatsApp() {
      const url = `https://api.whatsapp.com/send?phone=${encodeURIComponent(this.phoneNumber)}`;
      window.open(url, '_blank');
    }
  }
};
</script>

<style scoped>
.whatsapp-fab-desktop {
  transition: opacity 0.3s;
}

.whatsapp-fab-desktop.v-enter,
.whatsapp-fab-desktop.v-leave-to {
  opacity: 0;
}

.whatsapp-fab-mobile {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
</style>
