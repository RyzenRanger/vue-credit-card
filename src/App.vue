<template>
  <div id = "app">
    <transition name = "slide-fade">
      <credit-card v-if = 'isOpacity' :random-colors = 'colors' />
    </transition>
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
    isOpacity: true,
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
  background-image: url('@/assets/tired.gif');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 100%;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to{
  opacity: 0;
}
</style>
