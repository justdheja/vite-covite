<template>
  <div>
    <section class="hero is-fullheight">
      <div class="hero-body">
        <div class="container">
          <div class="columns">
            <div class="column text-place">
              <h1 class="title">
                covite
              </h1>
              <h2 class="subtitle">
                use your mask & wash your hand
              </h2>
              <slot></slot>
              <p class="subheading">Last Update: {{indonesiaConfirmed.lastUpdate}}</p>
              <br>
              <div class="columns">
                <div class="column">
                  <CardsItem title="Confirmed" :total="indonesiaConfirmed.confirmed.value"/>
                </div>
                <div class="column">
                  <CardsItem title="Recovered" :total="indonesiaConfirmed.recovered.value"/>
                </div>
                <div class="column">
                  <CardsItem title="Deaths" :total="indonesiaConfirmed.deaths.value"/>
                </div>
              </div>
            </div>
            <div class="column bg-mask">
              <img src="../assets/social_distancing.svg" alt="">
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import CardsItem from './CardsItem.vue'
export default {
  components: {
    CardsItem
  },
  props:{
    indonesiaConfirmed: Object
  }
}
</script>

<style lang="scss" scoped>

@import url('https://fonts.googleapis.com/css2?family=Merriweather&family=Pacifico&display=swap');

$pacifico : 'Pacifico', cursive;
$merriweather : 'Merriweather', serif;

.hero{
  background: #E0EAFC;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #CFDEF3, #E0EAFC);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #CFDEF3, #E0EAFC); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.text-place{
  text-align: left;
  justify-content: center;
  margin: auto;
}

h1{
  font-family: $merriweather;
}

.title{
  font-family: $pacifico;
  font-size: 10vh;
  font-weight: 200;
}

.subtitle{
  font-family: $merriweather;
  font-size: 2vh;
  margin-bottom: 50px;
}

.subheading{
  font-size: 2vh;
}

.bg-mask{
  text-align: center;
}

img{
  height: 50vh;
}
</style>