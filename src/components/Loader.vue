<template>
  <div class="loader">
      <img src="../assets/note.gif" alt="Loading">
  </div>
</template>

<script>
export default {
    name: "Loader"
}
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

    div {
        @include flex ($type: 'center');
        flex-direction: column;
        position: fixed;
        top: 0;
        height: 100%;
        width: 100%;
        z-index: 2;
        background-color: #fff;

        img {
            transition: animation .5s ease-in-out;
            animation: scale linear .6s infinite alternate;
        }
    }
    @keyframes scale {
        0% {
            transform: scale(1);
        }
        100% {
            transform: scale(1.2);
        }
    }
</style>