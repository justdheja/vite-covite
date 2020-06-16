<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  created() {
    fetch('https://covid19.mathdro.id/api/countries/indonesia')
      .then(response => response.json())
      .then(response => console.log(response))
  },
}
</script>
