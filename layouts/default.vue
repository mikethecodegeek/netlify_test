<template>
  <div class="container">
    <nuxt />
  </div>
</template>
 


<script>
import Logo from '~/components/Logo.vue'
import Nav from '~/components/Nav.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Logo, Nav, Footer
  },
  head() {
    return {
      link: [],
      script: [
        { src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }
      ]
    }
  }
}
</script>
