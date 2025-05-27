<template>
  <div>
    <h3>Yangi kino qo'shish</h3>
    <form class="add-form" @submit.prevent>
      <div class="d-flex gap-3">
        <input
          type="text"
          class="form-control new-movie-name"
          placeholder="Kino nomi?"
          v-model="name"
        />
        <input
          type="text"
          class="form-control new-movie-count"
          placeholder="Nechi marta ko'rilgan?"
          v-model="viewers"
        />
      </div>
      <div class="text-end mt-3">
        <button class="btn btn-outline-dark" @click="addMovie">Qo'shish</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: () => ({
    name: "",
    viewers: "",
  }),

  methods: {
    addMovie() {
      if (this.name && this.viewers) {
        this.$emit("add-movie", {
          id: Date.now(),
          name: this.name,
          viewers: this.viewers,
          like: false,
          favourite: false,
        });
        this.name = "";
        this.viewers = "";
      }
    },
  },
};
</script>

<style scoped></style>
