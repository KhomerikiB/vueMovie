<template>
  <div id="app" class="container">
    <Header />
    <Content />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
export default {
  name: "app",
  components: {
    Header,
    Content
  }
};
</script>

<style lang="scss">
@import "./styles/main.scss";
</style>
