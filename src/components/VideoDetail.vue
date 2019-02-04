<template>
  <div v-if="video" class="col-md-8">
    <div class="embed-responsive embed-responsive-16by9">
      <iframe class="embed-responsive-item" allowfullscreen :src="videoUrl"/>
    </div>
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
    },
    videoUrl() {
      const { videoId } = this.video.id;
      return `https://www.youtube.com/embed/${videoId}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.video-details {
  margin-top: 1rem;
  padding: 1rem;
  border: 0.1rem solid #dddddd;
  border-radius: 0.4rem;
}
</style>
