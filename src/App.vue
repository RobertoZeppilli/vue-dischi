<template>
  <div id="app">
    <Header
      :genres="selectedGenres"
      :authors="selectedAuthors"
      @updateData="update"
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
    update: function (genre, author) {
      this.activeGenre = genre;
  
      this.activeAuthor = author
    },
  },
};
</script>

<style lang="scss">
@import "./scss/general";
</style>
