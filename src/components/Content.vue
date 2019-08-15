<template>
  <div class="content">
    <div class="imagebox">
      <img src="../assets/layer.png" />
    </div>
    <div class="description">
      <p class="title">A Clockwork Orange</p>
      <p class="quote">
        Being the adventures of a young man
        whose principal interest is rape and violence
      </p>
      <p class="text">
        Demonic gang-leader Alex goes on the spree of rape, mugging
        and murder with his pack of "droogs". But he's a boy who also
        likes Beethoven's Ninth and a bit of "the old in-out, in-out".
        He later finds himself at the mercy
      </p>
      <div class="rates">
        <div class="rates-item flex-center">
          <div class="val flex-center">60</div>
          <div class="desc">
            <p class="title">METASCORE</p>
            <p class="web">
              From:
              <span>IMDB.COM</span>
            </p>
          </div>
        </div>
        <div class="rates-item flex-center">
          <img src="../assets/trending.png" />
          <div class="desc">
            <p class="title">POPULARITY</p>
            <div class="rates-val">126 20</div>
          </div>
        </div>
      </div>
      <Infobox />
    </div>
  </div>
</template>

<script>
import Infobox from "./Infobox.vue";
export default {
  name: "Content",
  components: {
    Infobox
  }
};
</script>

<style scoped>
</style>