<template>
  <table class="films-table">
    <tr>
      <th>Nombre</th>
      <th>Vista</th>
      <th></th>
    </tr>

    <AppFilm
      v-for="film in films"
      :key="film.name"
      :film="film"
      @delete-film="$emit('delete-film', $event)"
    ></AppFilm>
  </table>
</template>

<script>
import AppFilm from "./AppFilm";
export default {
  name: "AppFilmTable",
  props: {
    films: {
      type: Array,
      default: () => [],
    },
  },
  components: {
    AppFilm,
  },
  methods: {
    // deleteFilm($event) {
    //   this.$emit("delete-film", $event);
    //   console.log($event);
    // },
  },
};
</script>

<style>
.films-table {
  margin: 10px auto;
}

td {
  min-width: 60px;
}


</style>
