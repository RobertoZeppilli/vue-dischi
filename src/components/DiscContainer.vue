<template>
  <section class="container" v-if="!loaded">
    <div class="d-flex flex-wrap py-2">
      <Disc
        v-for="disc in filteredDiscs"
        :key="disc.id"
        :disc="disc"
        :poster="disc.poster"
        :title="disc.title"
        :author="disc.author"
        :year="disc.year"
      />
    </div>
  </section>
  <Loader v-else />
</template>

<script>
import Disc from "../components/Disc";
import Loader from "../components/Loader";
import axios from "axios";

export default {
  name: "DiscContainer",
  components: {
    Disc,
    Loader,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      discs: [],
      discGenres: [],
      discAuthors: [],
      loaded: true,
    };
  },
  props: {
    updatedGenre: String,
    updatedAuthor: String,
  },
  computed: {
    filteredDiscs() {
      if (this.updatedGenre == "" && this.updatedAuthor == "") {
        return this.discs;
      } else if (this.updatedAuthor != "") {
        return this.discs.filter((disc) => {
          return disc.author == this.updatedAuthor;
        });
      }
      return this.discs.filter((disc) => {
        return disc.genre == this.updatedGenre;
      });
    },
  },
  created() {
    axios.get(this.apiURL).then((response) => {
      this.discs = response.data.response;

      this.discs.forEach((disc) => {
        if (!this.discGenres.includes(disc.genre)) {
          this.discGenres.push(disc.genre);
        }
        if (!this.discAuthors.includes(disc.author)) {
          this.discAuthors.push(disc.author);
        }
      });

      this.$emit("discData", this.discGenres, this.discAuthors);
      setTimeout(() => {
        this.loaded = false;
      }, 2500);
    });
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

</style>