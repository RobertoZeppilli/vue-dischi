<template>
  <section>
    <div class="my-container" v-if="!loaded">
      <div
        v-for="disc in discs"
        :key="disc.id"
        class="disc-container"
      >
        <Disc :author="disc" />
      </div>
    </div>
  <Loader v-else/>
  </section>
</template>

<script>
import Disc from "../components/Disc";
import Loader from '../components/Loader';
import axios from "axios";

export default {
  name: "DiscContainer",
  components: {
    Disc,
    Loader
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      discs: [],
      loaded: true
    };
  },
  created() {
    axios.get(this.apiURL).then((response) => {
      this.discs = response.data.response;
      setTimeout(() => {
        this.loaded = false;
      }, 2000)
    });
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

section {
  height: 90vh;
  padding: 40px 0;
  background-color: $primaryBg;

  & > .my-container {
    @include flex ($type: 'center');
    flex-wrap: wrap;
    max-width: 900px;
    margin: 0 auto;
    height: 100%;

    & > .disc-container {
      height: 50%;
      width: calc(100% / 5);
      padding: 10px;
    }
  }
}

</style>