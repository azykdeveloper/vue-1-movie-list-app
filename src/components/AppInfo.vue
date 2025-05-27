<template>
  <div>
    <h3 class="text-uppercase">Barcha kinolar: {{ moviesCount }}</h3>
    <h4 class="text-uppercase">Eng ko'p ko'rilgan kinolar: {{ favouriteMoviesCount }}</h4>
  </div>
</template>

<script>
  export default {
    props: {
      moviesCount: {
        type: Number,
        required: true
      },
      favouriteMoviesCount: {
        type: Number,
        required: true
      }
    }
  }
</script>

<style scoped>

</style>