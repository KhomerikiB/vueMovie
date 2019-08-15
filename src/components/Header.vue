<template>
  <header class="search-container flex-space">
    <img src="../assets/logo.png" alt="The Movie DB" />
    {{searchInput}}
    <form>
      <input
        type="text"
        placeholder="Enter the movie name..."
        v-model="searchInput"
        class="search-input"
        v-on:input="onChange"
      />
    </form>
  </header>
</template>
<script>
export default {
  name: "Header",
  data() {
    return {
      searchInput: ""
    };
  },
  methods: {
    onChange() {
      console.log("onChange");
    }
  }
};
</script>

<style scoped lang="scss">
.search-input {
  font-size: 30px;
  font-family: "CircularStd-Book";
  border: none;
  cursor: pointer;
  outline: none;
  background-color: transparent;
  &::placeholder {
    color: #b4b4b4;
  }
}
</style>