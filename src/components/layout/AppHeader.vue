<template>
  <v-app-bar app color="primary" dark>
    <v-toolbar-title>{{ branding.appName }}</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn
      v-for="link in links"
      :key="`${link.label}-header-link`"
      text
      rounded
      :to="link.url"
    >{{ link.label }}</v-btn>
  </v-app-bar>
</template>
<script>
export default {
  props: {
    branding: Object,
    links: Array
  }
}
</script>
