<template>
  <div>
    <input placeholder="Search for videos" @input="onInput">
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(event) {
      this.$emit("termChange", event.target.value);
    }
  }
};
</script>

<style lang="scss" scoped>
div {
  text-align: center;
  margin: 2rem;

  input {
    width: 75%;
    font-size: 1.6rem;
    background: #201c29;
    border-radius: 27px;
    outline: 0;
    padding: 0.7rem 2.5rem 0.7rem 1.5rem;
    color: white;
    border-color: darkorange;
  }
}
</style>


