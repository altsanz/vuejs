<template>
  <tr>
    <td>{{ film.name }}</td>
    <td><input type="checkbox" v-model="film.seen" /></td>
    <td><button @click="deleteFilm">X</button></td>
  </tr>
</template>
<script>
export default {
  name: "AppFilm",
  props: {
    film: {
      type: Object,
    },
  },
  methods: {
    deleteFilm() {
      this.$emit("delete-film", this.film.name);
    },
  },
};
</script>
<style scoped></style>
