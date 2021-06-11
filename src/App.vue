<template>
  <div id="app">
    <Header
      :genres="selectedGenres"
      :authors="selectedAuthors"
      @newGenre="updateGenre"
      @newAuthor="updateAuthor"
      :watchGenre="activeGenre"
      :watchAuthor="activeAuthor"
    />
    <DiscContainer
      @discData="setData"
      :updatedGenre="activeGenre"
      :updatedAuthor="activeAuthor"
    />
  </div>
</template>

<script>
import Header from "./components/Header";
import DiscContainer from "./components/DiscContainer";

export default {
  name: "App",
  components: {
    Header,
    DiscContainer,
  },
  data() {
    return {
      selectedGenres: [],
      selectedAuthors: [],
      activeGenre: "",
      activeAuthor: ""
    };
  },
  methods: {
    setData: function (arrayGenres, arrayAuthors) {
      this.selectedGenres = arrayGenres;
      this.selectedAuthors = arrayAuthors;
    },
    updateGenre: function (genre) {
      this.activeGenre = genre;
      this.activeAuthor = "";
    },
    updateAuthor: function (author) {
      this.activeAuthor = author;
      this.activeGenre = "";

    }
  },
};
</script>

<style lang="scss">
@import "./scss/general";
</style>
