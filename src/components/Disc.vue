<template>
  <div class="disc">
    <div class="img-container">
      <img :src="author.poster" :alt="author.author" />
    </div>
    <!-- <div class="text-container text-center">
      <h4>{{ author.title }}</h4>
      <p>{{ author.author }}</p> 
      <p>{{ author.year }}</p> 
    </div> -->
  </div>
</template>

<script>
export default {
  name: "Disc",
  props: ["author"],
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

img {
    height: 50px;
}
</style>