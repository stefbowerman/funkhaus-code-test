<template>
  <div class="talent-item">
    <nuxt-link :to="`/talent/${ slug }`">
      <h3 class="talent-item__title">
        {{ title }}
      </h3>
      <div class="talent-item__bg" :style="{ backgroundImage: `url(/talent/${ image })` }" />
    </nuxt-link>
  </div>
</template>

<script type="text/javascript">
export default {
  props: {
    title: {
      type: String,
      default: null
    },
    slug: {
      type: String,
      default: null
    },
    image: {
      type: String,
      default: null
    }
  }
}
</script>

<style>
  .talent-item {
    display: flex;
    flex: 1;
    align-items: center;
    justify-content: center;
    position: relative;
    padding: 130px 30px;
    min-height: 400px;
    overflow: hidden;
    background-color: #000;
    text-align: center;
  }

  .talent-item a {
    color: #fff;
  }

  .talent-item__title,
  .talent-item__bg {
    transition: all 400ms ease-in-out;
  }

  .talent-item:hover .talent-item__title,
  .talent-item:hover .talent-item__bg {
    transition-duration: 200ms;
  }

  .talent-item__title {
    position: relative;
    z-index: 1;
    font-size: 55px;
    font-weight: normal;
  }

  .talent-item__bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    opacity: 0.6;
    background-size: cover;
    background-position: center;
  }

  .talent-item:hover .talent-item__title {
    transform: translateY(-3px);
  }

  .talent-item:hover .talent-item__bg {
    opacity: 0.8;
    transform: scale(1.02);
  }
</style>
