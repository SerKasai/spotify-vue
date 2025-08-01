<template>
  <div id="app">
    <MainHeader />
    <MainContent />
  </div>
</template>

<script>
import MainHeader from "./components/MainHeader.vue";
import MainContent from "./components/MainContent.vue";

export default {
  name: "App",
  components: {
    MainHeader,
    MainContent,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
