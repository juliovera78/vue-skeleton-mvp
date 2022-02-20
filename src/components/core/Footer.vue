<template>
  <v-footer height="60" class="d-block text-center">
    <div class="footer-items">
      <span v-for="link in links" :key="link.name">
        <!-- <a
          :href="link.Link"
          class="tertiary--text footer-links">{{ link.name }}</a> -->
        <div>version {{ appVersion }}</div>
      </span>
    </div>
    <v-spacer />
    <span
      v-for="link in links"
      :key="link.name"
      class="font-weight-light copyright"
    >
      &copy;
      {{ new Date().getFullYear() }}
      <a :href="link.Link" target="_blank">{{ link.name }}</a>
    </span>
  </v-footer>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
    links: [
      { name: 'piscomobile', Link: 'http://www.piscomobile.com/' }
      // { name: 'Demo', Link: 'https://clintoxx.github.io/vuetify-admin-dashboard/' },
      // { name: 'GitHub', Link: 'https://github.com/ClintOxx' }
    ]
  }),

  computed: {
    appVersion() {
      return this.$store.getters.appVersion
    }
  }
}
</script>
