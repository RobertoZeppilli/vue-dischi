<template>
  <div class="disc">
    <div class="img-container">
      <img :src="author.poster" :alt="author.author" />
    </div>
    <div class="text-container">
      <h4>{{ author.title }}</h4>
      <p>{{ author.author }}</p> 
      <p>{{ author.year }}</p> 
    </div>
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

.disc {
    height: 100%;
    padding: 20px;
    background-color: $secondaryBg;
    & > .img-container {
        height: 60%;
        @include flex ($type: 'center');

        & > img {
            height: 100%;
            object-position: center;
        }
    }
    .text-container {
        margin-top: 10px;
        text-align: center;
        & > h4 {
            margin-bottom: 10px;
            color: $primaryText;
            font-size: .9rem;
        } 
        & > p {
            color: $secondaryText;
            font-size: .7rem;
        }
    }
}
</style>