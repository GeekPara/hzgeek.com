<template>
  <v-app>
    <v-app-bar
      fixed
      app
      clipped-left
      elevate-on-scroll
      color="primary lighten-2"
    >
      <v-toolbar-title color="white">衡中极客圈</v-toolbar-title>
      <v-spacer />
      <v-btn icon @click="$vuetify.theme.dark = !$vuetify.theme.dark">
        <v-icon>{{
          $vuetify.theme.dark ? "mdi-weather-night" : "mdi-white-balance-sunny"
        }}</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
    <v-footer color="primary lighten-1" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link.title"
          color="white"
          text
          rounded
          class="my-2"
          :href="link.href"
          target="_blank"
        >
          {{ link.title }}
        </v-btn>
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} — <strong>HZGeek</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          title: "青章浚 B站",
          href: "https://space.bilibili.com/155369896",
        },
        {
          title: "YouXam 博客",
          href: "https://www.cnblogs.com/youxam",
        },
        {
          title: "AwAmeow 博客",
          href: "http://www.awameow.com"
        },
        {
          title:"Gary 博客",
          href:"https://www.cnblogs.com/rui-4825"
        },
        {
          title:"淘宝者 B站",
          href:"https://space.bilibili.com/500799994"
        }
        {
          title: "衡水中学",
          href: "http://hbhz.net/",
        },
      ],
    };
  },
};
</script>
