<template>
  <header>
      <div class="logo">
          <img class="ps-2" src="../assets/spotify.png" alt="Spotify Logo">
      </div>
  </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>

@import '../scss/variables';
@import '../scss/mixins';
    header {
        height: 10vh;
        background-color: $secondaryBg;
        & > .logo {
            height: 100%;
            @include flex ($type: 'default');
        }
        img {
            height: 50px;
        }
    }
</style>