<template>
  <div v-if="video">
    <div class="video-details">
      <h4>{{videoTitle}}</h4>
      <p>{{videoDescription}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    videoTitle() {
      return this.video.snippet.title;
    },
    videoDescription() {
      return this.video.snippet.description;
    }
  }
};
</script>

<style lang="scss" scoped>
  .video-details{
    margin-top: 1rem;
    padding: 1rem;
    border: .1rem solid #dddddd;
    border-radius: .4rem;
  }
</style>
