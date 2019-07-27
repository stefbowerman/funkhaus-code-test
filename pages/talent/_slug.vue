<template>
  <div>
    <Header />
    <div class="talent-wrapper">
      <div class="talent-sidebar talent-sidebar--left">
        <div class="talent-title">
          <span class="talent-title__accent">Talent</span>
          {{ title }}
        </div>
      </div>
      <div class="talent-sidebar talent-sidebar--right">
        <nuxt-link to="/">
          Close
        </nuxt-link>
      </div>

      <div class="talent-mini-header">
        <div class="container">
          <div class="talent-title">
            {{ title }}
          </div>
        </div>
      </div>

      <VideoPlayer :vimeo-id="project_vimeo_id" />

      <div class="container">
        <div class="project-titles">
          <h1 class="project-title">
            {{ project_title }}
          </h1>
          <h4 class="project-subtitle">
            {{ project_subtitle }}
          </h4>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/header.vue'
import Footer from '~/components/footer.vue'
import VideoPlayer from '~/components/videoPlayer.vue'
import talentData from '~/static/talentData.json'

export default {
  components: {
    Header,
    Footer,
    VideoPlayer
  },
  asyncData({ params }) {
    const filteredTalent = talentData.talent.filter((t) => {
      return t.slug === params.slug
    })

    return filteredTalent[0]
  }
}
</script>

<style>
.talent-wrapper {

}

@media (min-width: 800px) {
  .talent-wrapper {
    padding-left: 120px;
    padding-right: 120px;
  }
}

.talent-sidebar {
  display: none;
  position: fixed;
  top: 0;
  bottom: 0;
  height: 120px;
  width: 100vh;
  text-align: center;
  text-transform: uppercase;
  font-weight: bold;
}

.talent-sidebar--left {
  left: 0;
  transform: rotate(-90deg) translateX(-100%);
  transform-origin: top left;
}

.talent-sidebar--right {
  right: 120px;
  transform: rotate(-90deg) translateX(0);
  transform-origin: top right;
}

@media (min-width: 800px) {
  .talent-sidebar {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.talent-mini-header {
  display: block;
  text-align: center;
}

@media (min-width: 800px) {
  .talent-mini-header {
    display: none;
  }
}

.talent-title {
  text-transform: uppercase;
  font-weight: bold;
}

.talent-title__accent {
  display: inline-block;
  padding-right: 10px;
  color: #7d765b;
}

.project-titles {
  text-align: center;
  margin-top: 2rem;
}

.project-title {

}

.project-subtitle {
  color: #7d765b;
}

@media (max-width: 799px) {
  .project-title {
    font-size: 2.4rem;
  }

  .project-subtitle {
    font-size: 1.2rem;
  }
}
</style>
