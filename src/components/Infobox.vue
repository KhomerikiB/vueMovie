<template>
  <div class="infobox-item">
    <p class="title">GENRE</p>
    <p class="value">Science Fiction</p>

    <img src="../assets/theater.png" alt />
  </div>
</template>
<script>
export default {
  name: "Infobox",
  data() {
    return {
      imageName: ""
    };
  }
};
</script>
<style scoped lang="scss">
.infobox-item {
  height: 100px;
  background-color: #000;
  border-radius: 10px;
  overflow: hidden;
  position: relative;
  padding: 20px;
  line-height: 30px;
  img {
    position: absolute;
    top: 0;
    right: 0;
  }
  .title {
    color: #888888;
    font-size: 14px;
    font-family: "CircularStd-Bold";
  }
  .value {
    color: #fff;
    font-size: 30px;
    font-family: "CircularStd-Bold";
  }
}
</style>