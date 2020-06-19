<template>
  <div>
    <div v-show="!pageReady">
      <AppLoader/>
    </div>
    <div v-show="pageReady">
      <!-- <TheNavbar/> -->
      <TheHero :indonesiaConfirmed="response"  @ready="ready"/>
      {{response.confirmed.value}}
      {{response.lastUpdate}}
      <!-- <div v-for="nation in nations.countries" :key="nation.name">
        {{ nation.name }}
      </div> -->
      <TheFooter/>
    </div>
  </div>
</template>

<script>
import {IntersectingCirclesSpinner} from 'epic-spinners'
import AppLoader from './components/AppLoader.vue'
import TheNavbar from './components/TheNavbar.vue'
import TheHero from './components/TheHero.vue'
import TheFooter from './components/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheFooter,
    TheNavbar,
    TheHero,
    AppLoader
  },
  data() {
    return {
      response: null,
      nations: null,
      pageReady: false
    }
  },
  created() {
    fetch('https://covid19.mathdro.id/api/countries/indonesia')
      .then(response => response.json())
      .then(response => this.response = response)
    fetch('https://covid19.mathdro.id/api/countries/')
      .then(response => response.json())
      .then(response => this.nations = response)
    setTimeout(()=>{
      this.pageReady = true
    }, 2000)
  },
}
</script>

<style lang="scss">
@import url('./index.scss');
</style>
