<template>
  <v-footer color="primary lighten-1" padless>
    <v-layout justify-center wrap>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-footer-link`"
        text
        rounded
        color="white"
        :to="link.url"
      >{{ link.label }}</v-btn>
      <v-flex
        primary
        lighten-2
        py-4
        text-center
        white--text
        xs12
      >
        {{ new Date().getFullYear() }} —
        <strong>{{branding.appName}}</strong>
      </v-flex>
    </v-layout>
  </v-footer>
</template>
<script>
export default {
  props: {
    links: Array,
    branding: Object
  }
}
</script>
