<template>
  <div>
    <input @input="onInput">
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
  }
}
</style>


