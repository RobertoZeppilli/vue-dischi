<template>
  <section>
    <div class="container">
      <div class="row">
        <div v-for="disc in discs" :key="disc.id" class="col-6 col-md-2 col-lg-2">
          <Disc :author="disc" />
        </div>
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
}
</style>