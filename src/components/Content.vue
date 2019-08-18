<template>
  <div class="content">
    <div class="imagebox">
      <transition name="image-fade">
        <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + movie.poster_path" v-if="!loading" />
      </transition>
      <transition name="block-animation">
        <div class="block" v-if="!loading"></div>
      </transition>
    </div>
    <div class="description">
      <transition name="fade-title">
        <p class="title" v-if="!loading">{{movie.title}}</p>
      </transition>
      <transition name="fade-quote">
        <p class="quote" v-if="!loading">{{movie.tagline}}</p>
      </transition>
      <transition name="fade-overview">
        <p class="text" v-if="!loading">{{movie.overview}}</p>
      </transition>
      <transition name="fade-rates">
        <div class="rates" v-if="!loading">
          <div class="rates-item flex-center">
            <div class="val flex-center">{{movie.vote_average}}</div>
            <div class="desc">
              <p class="title" v-if="!loading">METASCORE</p>
              <p class="web">
                From:
                <span>IMDB.COM</span>
              </p>
            </div>
          </div>
          <div class="rates-item flex-center">
            <div class="popularity-imagebox">
              <img src="../assets/trending.png" />
            </div>
            <div class="desc">
              <p class="title">POPULARITY</p>
              <div class="rates-val">{{movie.popularity}}</div>
            </div>
          </div>
        </div>
      </transition>
      <div class="infobox-container">
        <transition name="fade-infobox1">
          <Infobox
            :info="movie.genres"
            title="GENRE"
            image="theater.png"
            bgcolor="bg-dark"
            v-if="!loading"
          />
        </transition>
        <transition name="fade-infobox2">
          <Infobox
            v-if="!loading"
            :info="movie.runtime+' minutes'"
            title="RUNTIME"
            image="clock-circular-outline.png"
            bgcolor="bg-brown"
          />
        </transition>
        <transition name="fade-infobox3">
          <Infobox
            :info="movie.revenue ? movie.revenue.toLocaleString() : ' '"
            title="BOX OFFICE"
            image="money-bag.png"
            bgcolor="bg-green"
            v-if="!loading"
          />
        </transition>
        <transition name="fade-infobox4">
          <Rating
            :imdb="movie.vote_average"
            title="VOTE AVERAGE"
            bgcolor="bg-gray"
            image="rate-star-button.png"
            v-if="!loading"
          />
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Infobox from "./Infobox.vue";
import Rating from "./Rating.vue";
export default {
  name: "Content",
  components: {
    Infobox,
    Rating
  },
  props: ["movie", "loading"],
  data() {
    return {
      revenue: ""
    };
  }
};
</script>

<style scoped>
.image-fade-enter-active {
  opacity: 0;
  animation-delay: 0.5s;
}
.block-animation-enter-active {
  animation: blockIn 0.4s, blockOut 0.3s 0.5s;
  animation-fill-mode: both;
}
.fade-title-enter-active {
  transition: all 0.7s;
}
.fade-quote-enter-active {
  transition: all 0.3s;
  transition-delay: 0.2s;
}
.fade-overview-enter-active,
.fade-rates-enter-active {
  transition: all 0.4s;
  transition-delay: 0.5s;
}
.fade-title-enter {
  opacity: 0;
  transform: translateY(15px);
}
.fade-quote-enter {
  opacity: 0;
  transform: translateY(10px);
  transition-delay: 0.2s;
}
.fade-overview-enter,
.fade-rates-enter {
  opacity: 0;
}
.fade-infobox1-enter-active,
.fade-infobox2-enter-active,
.fade-infobox3-enter-active,
.fade-infobox4-enter-active {
  transition: all 0.4s;
  transition-delay: 0.6s;
}

.fade-infobox1-enter,
.fade-infobox2-enter,
.fade-infobox3-enter,
.fade-infobox4-enter {
  opacity: 0;
}
@keyframes blockIn {
  0% {
    width: 0;
  }
  100% {
    width: 100%;
  }
}
@keyframes blockOut {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(100%);
  }
}
</style>