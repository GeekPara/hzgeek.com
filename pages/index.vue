<template>
  <v-container>
    <!--主体：宽屏-->
    <v-row class="my-16" v-if="$vuetify.breakpoint.mdAndUp">
      <v-col cols="2" offset="3">
        <v-img :src="logoImg"></v-img>
      </v-col>
      <v-col cols="4" align-self="center">
        <div class="my-4 ml-4">
          <img :src="nameImg" />
        </div>
        <p class="text-h6 text-secondery my-4 ml-4 text-no-wrap">
          {{ subtitle }}
        </p>
      </v-col>
    </v-row>
    <!--主体：窄屏-->
    <div v-else class="my-16">
      <v-row class="my-4">
        <v-col cols="6" offset="3">
          <v-img :src="logoImg"></v-img>
        </v-col>
      </v-row>
      <v-row class="my-4">
        <v-col cols="8" offset="2">
          <v-img :src="nameImg"></v-img>
        </v-col>
      </v-row>
      <v-row class="my-4">
        <v-col cols="12">
          <p class="text-center text-h6 text-secondery">
            {{ subtitle }}
          </p>
        </v-col>
      </v-row>
    </div>
    <!--介绍：宽屏-->
    <v-row v-if="$vuetify.breakpoint.mdAndUp" class="my-8">
      <v-col cols="4" v-for="item in contents" :key="item.title">
        <p class="text-h4">{{ item.title }}</p>
        <p class="text-body-1">{{ item.text }}</p>
      </v-col>
    </v-row>
    <!--介绍：窄屏-->
    <div v-else class="my-8">
      <v-row v-for="item in contents" :key="item.title">
        <v-col cols="10" offset="1">
          <p class="text-h4">{{ item.title }}</p>
          <p class="text-body-1">{{ item.text }}</p>
        </v-col>
      </v-row>
    </div>
    <!--链接：宽屏-->
    <v-row v-if="$vuetify.breakpoint.mdAndUp" class="my-8">
      <v-col cols="6" offset="3">
        <v-row>
          <v-col cols="4" v-for="item in buttons" :key="item.title">
            <v-btn :[item.type]="item.link" block x-large color="primary"
              ><v-icon left>{{ item.icon }}</v-icon
              >{{ item.title }}</v-btn
            >
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <!--链接：窄屏-->
    <div v-else class="my-8">
      <v-row>
        <v-col cols="8" offset="2" v-for="item in buttons" :key="item.title">
          <v-btn :[item.type]="item.link" block x-large color="primary"
            ><v-icon left>{{ item.icon }}</v-icon
            >{{ item.title }}</v-btn
          >
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  data: function () {
    return {
      logoImg: "/imgs/logo-zhang.png",
      subtitle: "衡水中学一群热爱计算机技术的极客们",
      contents: [
        {
          title: "我们是谁？",
          text: "我们是来自河北衡水中学四个校区、初高中两个学段的一群热爱计算机技术、有创新精神、有担当理想的学生。",
        },
        {
          title: "我们做啥？",
          text: "我们主要涉及编程开发、计算机技巧、软件分享、数码设备、智能硬件、视频影像、平面设计、音乐制作等各个方面。",
        },
        {
          title: "加入我们！",
          text: "我们欢迎任何衡中在校学生，只要你对计算机、数码有兴趣，无论你是小白还是大佬，点击网页底部链接加入我们！",
        },
      ],
      buttons: [
        {
          icon: "mdi-github",
          title: "GitHub",
          link: "https://github.com/HZ-Geek",
          type: "href",
        },
        {
          icon: "mdi-blogger",
          title: "博客动态",
          link: "/blog",
          type: "to",
        },
        {
          icon: "mdi-account-plus-outline",
          title: "加入我们",
          link: "https://joinus.hzgeek.com",
          type: "href",
        },
      ],
    };
  },
  computed: {
    nameImg: function () {
      return this.$vuetify.theme.dark
        ? "/imgs/name-dark.svg"
        : "/imgs/name.svg";
    },
  },
    head() {
    return {
      title: '首页',
    };
  },
};
</script>
