<template>
  <v-container>
    <v-row class="my-12">
      <v-col cols="6" md="2" offset="3" offset-md="3">
        <v-img src="/imgs/logo-zhang.png"></v-img>
      </v-col>
      <v-col cols="10" md="4" offset="1" offset-md="0" align-self="center">
        <p
          :class="{ 'text-center': !$vuetify.breakpoint.mdAndUp }"
          class="text-h3"
        >
          衡中极客圈
        </p>
        <p
          :class="{ 'text-center': !$vuetify.breakpoint.mdAndUp }"
          class="text-h6 text-secondery"
        >
          衡水中学一群热爱计算机技术的极客们。
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  components: {},
}
</script>
