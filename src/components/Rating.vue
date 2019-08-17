<template>
  <div class="infobox-item" :class="bgcolor">
    <p class="title">{{title}}</p>
    <div class="flexbox">
      <div class="ratings">
        <div class="empty-stars"></div>
        <div
          class="full-stars"
          :style="{'width':imdb.toString().indexOf('.') !== -1 ? imdb.toString().split('.').join('') +'%': imdb.toString() +'0%'}"
        ></div>
      </div>
      <span class="imdb">{{imdb}}</span>
    </div>
    <img :src="require('../assets/'+image)" alt />
  </div>
</template>

<script>
export default {
  name: "Rating",
  props: ["bgcolor", "title", "image", "imdb", "percent"]
};
</script>
<style scoped>
.ratings {
  position: relative;
  vertical-align: middle;
  display: inline-block;
  color: #d6c3b9;
  overflow: hidden;
}

.full-stars {
  position: absolute;
  left: 0;
  top: 0;
  white-space: nowrap;
  overflow: hidden;
}

.empty-stars:before,
.full-stars:before {
  content: "\2605\2605\2605\2605\2605";
  font-size: 30px;
}

.full-stars {
  color: #fff;
}
.imdb {
  font-size: 20px;
  color: #fff;
  font-family: "CircularStd-Bold";
  position: relative;
  z-index: 2;
  margin-left: 10px;
}
img {
  position: absolute;
  top: 0;
  right: -25px;
  height: 100%;
}
</style>