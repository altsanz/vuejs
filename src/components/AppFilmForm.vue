<template>
  <div>
    <input type="text" :value="inputName" @input="updateText" />
    <button @click="submitFilm" :disabled="inputName.length === 0">
      Añadir
    </button>
  </div>
</template>

<script>
export default {
  name: "AppFilmForm",
  data() {
    return {
      inputName: "",
    };
  },
  methods: {
    updateText(value) {
      this.inputName = value.target.value;
    },
    submitFilm() {
      this.$emit("new-film", this.inputName);
      this.inputName = "";
    },
  },
};
</script>

<style scoped>
</style>
