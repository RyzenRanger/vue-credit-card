<template>
  <div id = "app">
    <video autoplay muted loop class = "video-background">
      <source src="@/assets/calling20221009.mp4" type="video/mp4">
    </video>

    <credit-card />
  </div>
</template>

<script>
import CreditCard from '@/components/CreditCard.vue'

export default {
  name: 'App',

  components: { CreditCard },
}
</script>

<style lang = 'scss'>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}

.video-background {
  position: fixed;
  top: 0;
  left: 0;
}
</style>
