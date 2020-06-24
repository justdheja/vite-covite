<template>
  <div>
    <div class="card">
      <div class="card-content">
          <div class="title">
            {{total}}
          </div>
          <div class="subtitle">
            {{title}}
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    total: {
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
$card-height: 100px;

.subtitle{
  font-size: 2vh;
}

.title{
  font-size: 5vh;
}

.card{
  height: $card-height;
  transition: 1s;
  position: center;
}
</style>