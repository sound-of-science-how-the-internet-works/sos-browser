<template lang="pug">
div
  error(v-if=" ! desktop.valid", :domain="desktop.domain", :tld="desktop.tld")
  img(v-if="desktop.valid", :src="images[desktop.domain + '.' + desktop.tld]")
</template>

<script>
import error from '~/components/error.vue'
export default {
  name: 'Index',
  components: {
    error
  },
  data() {
    return {
      desktop: {
        valid: true,
        domain: 'nucleus.be'
      },
      images: {
        'nucleus.be': '/images/nucleus.be.png',
        'combell.be': '/images/combell.be.png'
      }
    }
  },
  created() {
    this.$store.dispatch('states/find', {}).then(data => {
      this.desktop = data.data[0]
    })
  }
}
</script>

<style lang="postCss">

</style>
