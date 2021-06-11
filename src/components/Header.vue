<template>
  <header class="d-flex align-items-center justify-content-between px-2">
    <div class="logo">
      <img src="../assets/spotify.png" alt="Spotify Logo" />
    </div>
    <div class="select-container">
      <select v-model="selectGenre" @change="$emit('newGenre', selectGenre)">
        <option value="">Seleziona un genere</option>
        <option v-for="(genre, index) in genres" :key="index" :value="genre">
          {{ genre }}
        </option>
      </select>
      <select v-model="selectAuthor" @change="$emit('newAuthor', selectAuthor)">
        <option value="">Seleziona un artista</option>
        <option v-for="(author, index) in authors" :key="index" :value="author">
          {{ author }}
        </option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      selectGenre: "",
      selectAuthor: "",
    };
  },
  props: {
    genres: Array,
    authors: Array,
    watchGenre: String,
    watchAuthor: String,
  },
  watch: {
    watchGenre: function (val) {
      this.selectGenre = val;
    },
    watchAuthor: function (val) {
      this.selectAuthor = val;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

header {
  height: 80px;
  background-color: $secondaryBg;

  img {
    height: 50px;
  }
  select {
    margin-left: 10px;
    padding: 10px;
    transition: all 0.5s ease-in-out;
    outline: none;
    border: none;
    border-radius: 0 10px 0 10px;
    background-color: lighten($primaryBg, 10%);
    color: $primaryText;
    &:hover {
      border-radius: 10px 0 10px 0;
    }
  }
}
</style>