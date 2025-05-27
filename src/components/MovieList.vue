<template>
  <ul class="list-group">
    <MovieListItem
      v-for="movie in movies"
      :key="movie.id"
      :movie="movie"
      @onToggle="$emit('onToggle', $event)"
      @onRemove="$emit('onRemove', $event)"
    />
  </ul>

</template>

<script>
import MovieListItem from "./MovieListItem.vue";
export default {
  components: {
    MovieListItem,
  },
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
