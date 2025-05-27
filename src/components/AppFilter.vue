<template>
  <div class="btn-group mt-3">
    <button
      v-for="btn in buttons"
      :key="btn.value"
      class="btn"
      :class="filter === btn.value ? 'btn-dark' : 'btn-outline-dark'"
      @click="onFilter(btn.value)"
    >
      {{ btn.label }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filter: "all",
      buttons: [
        { value: "all", label: "Barcha kinolar" },
        { value: "popular", label: "Mashxur" },
        { value: "most-viewed", label: "Eng ko'p ko'rilgan kinolar" }
      ]
    };
  },
  props: {
    onUpdateFilter: {
      type: Function,
      required: true
    }
  },
  methods: {
    onFilter(filter) {
      this.filter = filter;
      this.onUpdateFilter(filter);
    },
  }
};
</script>

<style scoped>
/* Custom styling if needed */
</style>
