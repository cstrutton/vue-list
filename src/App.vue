<template>
  <div id="app">
    <v-app>
      <app-header :links="links" :branding="branding" />
      <v-content>
        <router-view />
      </v-content>
      <app-footer :links="links" :branding="branding" />
    </v-app>
  </div>
</template>

<script>
import AppHeader from '@/components/layout/AppHeader.vue'
import AppFooter from '@/components/layout/AppFooter.vue'

export default {
  name: 'App',

  components: {
    AppHeader,
    AppFooter
  },

  data: () => ({
    branding: {
      appName: 'Vue List'
    },
    links: [
      { label: 'Home', url: '/' },
      { label: 'About', url: '/about' }
    ]
    //
  })
}
</script>
