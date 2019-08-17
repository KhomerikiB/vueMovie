<template>
  <div class="infobox-item" :class="bgcolor">
    <p class="title">{{title}}</p>
    <div class="outer" v-if="Array.isArray(info)">
      <p class="value" :key="item.id" v-for="item in info.slice(0,2)">{{item.name}}</p>
    </div>
    <p class="value" v-else>{{info}}</p>
    <img :src="require('../assets/'+image)" alt />
  </div>
</template>
<script>
export default {
  name: "Infobox",
  props: ["info", "title", "image", "bgcolor"],
  data() {
    return {
      imageName: ""
    };
  }
};
</script>
<style  lang="scss">
.infobox-item {
  height: 100px;
  border-radius: 10px;
  overflow: hidden;
  position: relative;
  padding: 20px;
  line-height: 30px;
  margin-bottom: 30px;
  .outer {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    line-height: 40px;
    position: relative;
    z-index: 5;
  }
  img {
    position: absolute;
    top: 0;
    right: 0;
  }
  .title {
    color: #fff;
    opacity: 0.7;
    font-size: 14px;
    font-family: "CircularStd-Bold";
  }
  .value {
    color: #fff;
    font-size: 20px;
    font-family: "CircularStd-Bold";
    &:not(:last-child) {
      margin-right: 7px;
    }
  }
}
</style>