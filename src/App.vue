<template>
  <div id = "app">
    <video autoplay muted loop class = "video-background">
      <source src="@/assets/background-anime.mp4" type="video/mp4">
    </video>

    <credit-card :random-colors = 'colors' />
    <button-random-gradient @new-gradient = "saveGradient" />
  </div>
</template>

<script>
import CreditCard from '@/components/CreditCard.vue'
import ButtonRandomGradient from '@/components/ButtonRandomGradient.vue';

export default {
  name: 'App',

  components: { CreditCard, ButtonRandomGradient },

  data: () => ({
    colors: {},
  }),

  methods: {
    saveGradient (randomColors) {
      this.colors = randomColors;
    }
  }
}
</script>

<style lang = 'scss'>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Cera Pro Medium';
}

@font-face {
	font-family: 'Cera Pro Medium';
	src: url('@/assets/fonts/CeraPro-Medium.eot'); //CeraPro-Thin.eot
	src: url('@/assets/fonts/CeraPro-Medium.eot?#iefix') format('embedded-opentype'),
	url('@/assets/fonts/CeraPro-Medium.woff') format('woff'),
	url('@/assets/fonts/CeraPro-Medium.ttf') format('truetype');
	font-weight: normal;
	font-style: normal;
}

#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}

.video-background {
  position: fixed;
  z-index: -999;
  top: 0;
  left: 0;
}
</style>
