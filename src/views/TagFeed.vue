<template>
  <div class="home-page">
    <mcv-banner />
    <div class="container papge">
      <div class="row">
        <div class="col-md-9">
          <mcv-feed :api-url="apiUrl" />
        </div>
        <div class="col-md-3">
          <mcv-popular-tags />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import McvFeed from '@/components/Feed'
import McvPopularTags from '@/components/PopularTags'
import McvBanner from '@/components/Banner'

export default {
  name: 'McvYourFeed',
  components: {
    McvFeed,
    McvPopularTags,
    McvBanner
  },
  computed: {
    apiUrl() {
      const tagName = this.$route.params.slug
      return `/articles?tag=${tagName}`
    }
  }
}
</script>
