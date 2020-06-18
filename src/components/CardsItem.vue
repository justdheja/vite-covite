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
.subtitle{
  font-size: 2vh;
}

.card{
  height: 20vh;
}
</style>