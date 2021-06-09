<template>
  <div id="app">
    <Header />
    <DiscContainer />
  </div>
</template>

<script>
import Header from "./components/Header";
import DiscContainer from './components/DiscContainer';

export default {
  name: "App",
  components: {
    Header,
    DiscContainer
  }
};
</script>

<style lang="scss">
@import "./scss/general";



</style>
