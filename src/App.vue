<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  computed: {},
  created() {
    this.$store.dispatch("checkUser");
  }
};
</script>

<style lang="scss">
#app {
  height: 100vh;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
}
</style>
