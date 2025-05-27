<template>
  <div>
    <input
      type="text"
      class="form-control search-input"
      placeholder="Kinolarni qidirish"
      v-model="term"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      term: "",
    };
  },
  props: {
    onUpdateTerm: {
      type: Function,
      required: true,
    },
  },
  watch: {
    term(newVal) {
      this.onUpdateTerm(newVal);
    },
  },
};
</script>

<style scoped></style>
