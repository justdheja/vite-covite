<template>
  <!-- <TheNavbar/> -->
  <TheHero/>
  {{response.confirmed.value}}
  {{response.lastUpdate}}
  <!-- <div v-for="nation in nations.countries" :key="nation.name">
    {{ nation.name }}
  </div> -->
  <TheFooter/>
</template>

<script>
import TheNavbar from './components/TheNavbar.vue'
import TheHero from './components/TheHero.vue'
import TheFooter from './components/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheFooter,
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
