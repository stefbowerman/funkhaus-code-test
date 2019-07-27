<template>
  <div>
    <Header />
    <div class="container">
      <h1 class="title">
        Talent
      </h1>

      <div class="grid">
        <div v-for="(t, index) in talent" :key="index" class="grid-item">
          <TalentItem :title="t.title" :slug="t.slug" :image="t.featured_image" />
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/header.vue'
import Footer from '~/components/footer.vue'
import TalentItem from '~/components/talentItem.vue'
import talent from '~/static/talentData.json'

export default {
  components: {
    Header,
    Footer,
    TalentItem
  },
  data() {
    return talent
  }
}
</script>

<style>
.title {
  display: block;
  margin: 7rem 0;
  font-size: 154px;
  font-size: calc(80px + 3.5vw);
  font-weight: 900;
  text-align: center;
}

.grid {
  display: flex;
  flex-wrap: wrap;
}

.grid-item {
  display: flex; /* equal height items */
  flex-basis: 100%;
}

@media (min-width: 700px) {
  .grid-item {
    flex-basis: 50%;
  }
}
</style>
