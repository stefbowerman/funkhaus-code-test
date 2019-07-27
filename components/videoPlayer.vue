<template>
  <div class="video-player">
    <iframe
      :src="`https://player.vimeo.com/video/${vimeoId}`"
      width="100%"
      frameborder="0"
      allow="autoplay; fullscreen"
      allowfullscreen=""
    />
  </div>
</template>

<script>
export default {
  props: {
    vimeoId: {
      type: Number,
      default: null
    }
  }
}
</script>

<style>
.video-player {
  position: relative;
  padding-bottom: 56.25%; /* 16:9 */
  padding-top: 25px;
  height: 0;
}

.video-player iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
