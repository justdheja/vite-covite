<template>
  <TheNavbar/>
  <TheHero/>
  <img alt="Vue logo" src="./assets/logo.png" />
  {{response.confirmed.value}}
  <div v-for="nation in nations.countries" :key="nation.name">
    {{ nation.name }}
  </div>
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import TheNavbar from './components/TheNavbar.vue'
import TheHero from './components/TheHero.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheNavbar,
    TheHero
  },
  data() {
    return {
      response: null,
      nations: null
    }
  },
  created() {
    fetch('https://covid19.mathdro.id/api/countries/indonesia')
      .then(response => response.json())
      .then(response => this.response = response)
    fetch('https://covid19.mathdro.id/api/countries/')
      .then(response => response.json())
      .then(response => this.nations = response)
  },
}
</script>

<style lang="scss">
@import url('./index.scss');
</style>
