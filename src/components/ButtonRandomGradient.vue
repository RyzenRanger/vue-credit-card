<template>
  <button @click = "sendColors()">random gradient</button>
</template>

<script>
export default {
  name: 'button-random-gradient',

  methods: {
    sendColors () {
      this.$emit('new-gradient', {
        first: { r: this.generateColor(0, 255), g: this.generateColor(0, 255), b: this.generateColor(0, 255) },
        second: { r: this.generateColor(0, 255), g: this.generateColor(0, 255), b: this.generateColor(0, 255) }
      })
    },
    generateColor (min, max) {
      return min + Math.floor(Math.random() * (max - min + 1));
    }
  }
}
</script>

<style scoped lang = 'scss'>
button {
  all: unset;
  background: rgba(250, 250, 250, 0.6);
  padding: 10px 15px;
  border-radius: 15px;
  text-transform: uppercase;
  transition: 0.3s;
  
  &:hover {
    cursor: pointer;
    color: #FFFFFF;
    background-color: rgba(0, 0, 0, 0.6);
  }
}
</style>
