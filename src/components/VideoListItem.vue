<template>
  <div>
    <li class="list-group-item media" @click="onVideoSelect">
      <img class="video-thumbail mr-3" :src="smallThumbnailURL">
      <div class="media-body">
        <p class="video-title">{{videoTitle}}</p>
      </div>
    </li>
  </div>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    smallThumbnailURL() {
      return this.video.snippet.thumbnails.default.url;
    },
    videoTitle() {
      return this.video.snippet.title;
    }
  },
  methods : {
    // Passes video to parent component 
    onVideoSelect () {   
      this.$emit('videoSelect', this.video)
    }
  }
};
</script>

<style lang="scss" scoped>
.list-group-item {
  display: flex;
  cursor: pointer;

  &:hover {
    background: #eeeeee;
  }

  .video-title {
    font-size: 1.6rem;
  }
}
</style>
