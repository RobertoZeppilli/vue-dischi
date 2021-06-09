<template>
  <section>
    <div class="my-container">
      <div
        v-for="disc in discs"
        :key="disc.id"
        class="disc-container"
      >
        <Disc :author="disc" />
      </div>
    </div>
  </section>
</template>

<script>
import Disc from "../components/Disc";
import axios from "axios";

export default {
  name: "DiscContainer",
  components: {
    Disc,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      discs: [],
    };
  },
  created() {
    axios.get(this.apiURL).then((response) => {
      this.discs = response.data.response;
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
    max-width: 1000px;
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