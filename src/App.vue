<template>
  <div id="app">
    <h1>Diario de películas</h1>
    <AppFilmForm v-on:new-film="addFilm"></AppFilmForm>
    <AppFilmTable :films="films" @delete-film="deleteFilm"></AppFilmTable>
  </div>
</template>

<script>
import AppFilmForm from "./components/AppFilmForm";
import AppFilmTable from "./components/AppFilmTable";
export default {
  name: "App",
  components: {
    AppFilmForm,
    AppFilmTable,
  },
  data: function () {
    return {
      films: [
        { name: "El Gran Hotel Budapest", seen: false },
        { name: "Interstellar", seen: true },
      ],
    };
  },
  methods: {
    addFilm($event) {
      this.films.push($event);
    },
    deleteFilm($event) {
      console.log($event);
      this.films = this.films.filter((film) => film.name !== $event);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
