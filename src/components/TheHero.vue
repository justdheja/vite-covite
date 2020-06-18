<template>
  <div>
    <section class="hero is-fullheight">
      <div class="hero-body">
        <div class="container">
          <div class="columns">
            <div class="column text-place">
              <h1 class="title">
                new normal
              </h1>
              <h2 class="subtitle">
                Brace yourself new normal is coming
              </h2>
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


.title{
  font-family: $pacifico;
  color: black;
}

.subtitle{
  font-family: $merriweather;
  font-size: 3vh;
}

.bg-mask{
  text-align: center;
}

img{
  height: 50vh;
}
</style>