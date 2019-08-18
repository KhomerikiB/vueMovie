<template>
  <header class="flex-space">
    <div class="imagebox" id="header-logo-box">
      <a href="/">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="73"
          height="64"
          viewBox="0 0 73 64"
        >
          <image
            id="Logo"
            width="73"
            height="64"
            xlink:href="data:img/png;base64,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"
          />
        </svg>
      </a>
    </div>
    <form @submit.prevent="onSubmit">
      <div class="input-container">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="26"
          height="26"
          viewBox="0 0 26 26"
          id="search-icon"
        >
          <image
            id="search"
            width="26"
            height="26"
            xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAaCAYAAACpSkzOAAACKElEQVRIibXVT4iNURjH8Y8xEQuFkfInC6QoRQmZhX9DEdkoZCGyGtkaEmGByIasWEgKC2WMP1EiEklYKAuJRKLJWEj+6+hcPW7ve8fM5Ve3zu/c97zf8zznPc/Tp6OjQ4n6Yg4WYiKG4Rte4yHO427Z4mo1Fsw1YA22YUzJumXYjvvYgkvdgRqqfBMu42gB5Ct+VM1NwUUcQb+/BaXU3MS8MHcdqzEyvyj9xqIVj8Jz69BRC1YBpRSewYTsu7AUs3ECr3I0KaqnOIzJ2IgveU0LDnUH2oDmPO7ETJyrlQp8x0EsDrD1mFsG6o+tYW4tHncDibqCHcHvLAOlHQ3NPp1Jew8gFR3I6U2ahXFFoPnBH+8FJOkjTgffUgQaH/ytXoKSbofx2CLQ4ODf1AGKa4cUgd4H31QHaFgYvy0CPQl+Wh2gqWH8vAh0LfiVvYSkC78i+MtFoPaQvkW5YvdUraE23qnK0m/QB+wPc8cwqgeQ6dgdfOmFTdqHB3k8Ou+quWhBlVbhKgZkn+7ShVqgT7nHvMx+BG7gFBbkMlXRICzPZ5sK7sDwX6zof6i6w6ZozuY+E/Uj35PGUK7KtBl7yiKq6AVm5Ic744YwvADyLH+pe8NcOq+2alBRK/+cd5RawJKcukkZ9ClHdi931iu5XZzMazcFmBhZEaiiD/kFJ2s8E1WJohBWnbp61VaWxloR1QNLipF1/euIIixGtup/RBRh7359UOz6CRjpbmUtj5JrAAAAAElFTkSuQmCC"
          />
        </svg>
        <input
          type="text"
          placeholder="Enter the movie name..."
          v-model="searchInput"
          class="search-input"
          ref="input"
          @input="onChange"
          @focus="focus"
        />
      </div>

      <div class="search-results" ref="search-results">
        <p :key="item.id" v-for="item in movieItems" @click="itemOnClick(item.id)">{{item.title}}</p>
      </div>
    </form>
    <div id="bg" ref="bg" class="fixed-bg" @click="unfocus">
      <div class="container gray">
        <div class="flex">
          <div class="left"></div>
          <div class="right"></div>
        </div>
        <div class="full"></div>
      </div>
    </div>
  </header>
</template>
<script>
import axios from "axios";
export default {
  name: "Header",
  data() {
    return {
      searchInput: "",
      movieItems: []
    };
  },
  methods: {
    onChange() {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=${
            process.env.VUE_APP_KEY
          }&query=${
            this.searchInput.length > 0 ? this.searchInput : " "
          }&page=1&include_adult=false`
        )
        .then(response => {
          return response.data;
        })
        .then(data => {
          this.movieItems = data.results.splice(0, 3);
        });
    },
    focus() {
      const bg = this.$refs["bg"];
      bg.classList.add("visible");
      this.$refs["search-results"].classList.add("active");
    },
    onSubmit(e) {
      if (this.movieItems.length > 0 && this.searchInput.length > 0) {
        this.$emit("movieName", this.searchInput);
        this.$refs["input"].blur();
        this.unfocus();
        this.searchInput = "";
      }
    },
    itemOnClick(id) {
      this.$emit("movieId", id);
      this.searchInput = "";
      this.unfocus();
    },
    unfocus(e) {
      this.$refs["bg"].classList.remove("visible");
      this.$refs["search-results"].classList.remove("active");
    }
  }
};
</script>

<style scoped lang="scss">
header .imagebox {
  width: 500px;
}
form {
  position: relative;
  flex: 1;
  height: 200px;
  display: flex;
  align-items: center;
  padding-left: 70px;
  z-index: 40;
}
#search-icon {
  pointer-events: none;
}
.search-results {
  z-index: 30;
  position: absolute;
  top: 100%;
  background-color: #fff;
  width: 600px;
  left: 0;
  transition: all 0.1s ease-in;
  z-index: 25;
  opacity: 0;
  pointer-events: none;
  &.active {
    pointer-events: fill;
    opacity: 1;
  }
  p {
    font-family: "CircularStd-Book";
    padding: 20px 140px;
    font-size: 30px;
    color: #000000;
    cursor: pointer;
    &:first-child {
      padding-top: 50px;
    }
    &:last-child {
      padding-bottom: 50px;
    }
  }
}
.input-container {
  position: relative;
  width: 100%;
  svg {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
  }
}
.search-input {
  width: 100%;
  height: 100%;
  font-size: 30px;
  padding-left: 70px;
  font-family: "CircularStd-Book";
  border: none;
  cursor: pointer;
  color: #000;
  outline: none;
  background-color: transparent;
  &::placeholder {
    color: #b4b4b4;
  }
}
</style>