<template>
  <div id="app">
    <div class="container">
      <Header @movieName="recieveName($event)" v-on:movieId="recieveId($event)" />
      <Content :movie="movie" :loading="loading" />
    </div>
    <div
      class="bg-image"
      v-if="!loading"
      v-bind:style="{ backgroundImage: 'url(http://image.tmdb.org/t/p/original/' + backdropimage + ')' }"
    >
      <div class="left"></div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
export default {
  name: "app",
  components: {
    Header,
    Content
  },
  data() {
    return {
      movie: [],
      loading: true,
      backdropimage: ""
    };
  },
  methods: {
    getMovieById(id) {
      this.loading = true;
      axios
        .get(
          `https://api.themoviedb.org/3/movie/${id}?api_key=941d2ab6394c4f9fbe9549d7a350b234&language=en-US`
        )
        .then(response => {
          return response.data;
        })
        .then(data => {
          this.movie = data;
          this.loading = false;
          this.backdropimage = data.backdrop_path;
        })
        .catch(err => {
          this.loading = true;
        });
    },
    recieveName(data) {
      axios
        .get(
          `
https://api.themoviedb.org/3/search/movie?api_key=941d2ab6394c4f9fbe9549d7a350b234&language=en-US&query=${data}&page=1&include_adult=false`
        )
        .then(response => {
          return response.data;
        })
        .then(data => {
          console.log(data);
          if (data.results.length > 0) {
            console.log("exec");
            this.getMovieById(data.results[0].id);
          }
        });
    },
    recieveId(id) {
      this.getMovieById(id);
    }
  },
  created() {
    let randomYear = Math.floor(Math.random() * (2019 - 1995)) + 1995;
    let randomNumber = Math.floor(Math.random() * 10) + 1;
    axios
      .get(
        `https://api.themoviedb.org/3/discover/movie?api_key=941d2ab6394c4f9fbe9549d7a350b234&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&primary_release_year=${randomYear}

`
      )
      .then(response => {
        return response.data;
      })
      .then(data => {
        this.getMovieById(data.results[randomNumber].id);
      });
  }
};
</script>

<style lang="scss">
@import "./styles/main.scss";
</style>
