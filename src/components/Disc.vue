<template>
  <div class="disc d-flex flex-column justify-content-between text-center">
    <div class="disc-data">
      <img class="mb-2" :src="poster" :alt="author" />
      <h4 class="mb-4 lead">{{ title }}</h4>
    </div>
    <div class="text-container">
      <h4 class="text-muted">{{ author }}</h4>
      <h5 class="text-muted">{{ year }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "Disc",
  props: ["disc", "poster", "author", "title", "year"],
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";

.disc {
  width: calc(100% / 5 - 1rem);
  background-color: $secondaryBg;
  padding: 10px;
  margin: 0.5rem;

  img {
    width: 100%;
  }
  h4 {
    color: $primaryText;
    font-size: 1.2em;
    font-weight: 800;
  }
}
</style>