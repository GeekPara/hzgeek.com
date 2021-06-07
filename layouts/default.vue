<template>
  <v-app>
    <v-app-bar fixed app clipped-left elevate-on-scroll>
      <v-toolbar-title>衡中极客圈</v-toolbar-title>
      <v-spacer />
      <v-btn icon @click="$vuetify.theme.dark = !$vuetify.theme.dark">
        <v-icon>{{
          $vuetify.theme.dark ? 'mdi-weather-night' : 'mdi-white-balance-sunny'
        }}</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
    <v-footer>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
