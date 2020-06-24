<template>
  <div>
    <div v-show="!pageReady">
      <AppLoader/>
    </div>
    <div v-show="pageReady">
      <!-- <TheNavbar/> -->
      <TheHero :indonesiaConfirmed="response"/>
      <div class="control has-icons-left">
        <div class="select">
          <select @click="selectData()" v-model="selectedNation">
            <option selected :value=null>
              Global
            </option>
            <option @click="selectData()" v-for="nation in nations.countries" :key="nation.name" :value="nation.name">
              {{ nation.name }}
            </option>
          </select>
        </div>
        <span class="icon is-left">
          <i class="fas fa-globe"></i>
        </span>
      </div>
      {{selectedNation}}
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
      pageReady: false,
      selectedNation: null
    }
  },
  methods:{
    selectData(){
      if(this.selectedNation!=null){
        if(this.selectedNation === "CZ"){
          fetch(`https://covid19.mathdro.id/api/countries/czechia`)
            .then(response => response.json())
            .then(response => this.response = response)
        } else {
          fetch(`https://covid19.mathdro.id/api/countries/${this.selectedNation}`)
            .then(response => response.json())
            .then(response => this.response = response)
        }
      } else {
        fetch(`https://covid19.mathdro.id/api/`)
          .then(response => response.json())
          .then(response => this.response = response)
      }
    }
  },
  created() {
    fetch('https://covid19.mathdro.id/api/')
      .then(response => response.json())
      .then(response => {
        this.response = response
        setTimeout(()=>{
          this.pageReady = true
        }, 2000)
        
      })
    fetch('https://covid19.mathdro.id/api/countries/')
      .then(response => response.json())
      .then(response => this.nations = response)
  },
}
</script>

<style lang="scss">
@import url('./index.scss');
</style>
