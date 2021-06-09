<template>
  <div class="loader">
    <img src="../assets/note.gif" alt="Loading" />
    <p>Music is Everything</p>
  </div>
</template>

<script>
export default {
  name: "Loader",
};
</script>

<style lang="scss" scoped>
@import "../scss/variables";
@import "../scss/mixins";

div {
  @include flex($type: "center");
  flex-direction: column;
  position: fixed;
  top: 0;
  height: 100%;
  width: 100%;
  z-index: 2;
  background-color: #fff;

  img {
    transition: animation 0.5s ease-in-out;
    animation: scale ease-in-out 0.6s infinite alternate;
    margin-bottom: 50px;
  }
  p {
    font-size: 2rem;
    padding: 0 5px;
    position: relative;
    &::after,
    &::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      height: 100%;
      
    }
    &::before {
      background-color: #fff;
      animation: typeAnimation 2s steps(19) 0.5s forwards;
    }
    &::after {
      width: 0.125em;
      background-color: #333;
      animation: typeAnimation 2s steps(19) 0.5s forwards, cursorEffect 500ms steps(19) infinite;
    }
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
@keyframes typeAnimation {
  to {
    left: 100%;
  }
}
@keyframes cursorEffect {
  to {
    background-color: transparent;
  }
}
</style>