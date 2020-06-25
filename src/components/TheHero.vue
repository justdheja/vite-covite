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
                Brace yourself new normal is coming
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
$bg-hero : #F5F4F4;

.hero{
  background: $bg-hero;
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
  font-size: 3vh;
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