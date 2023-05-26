<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-light-blue-4">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> deuteridayo's Website dayo </q-toolbar-title>

        <!-- <div>Quasar v{{ $q.version }}</div> -->
      </q-toolbar>
    </q-header>

    <q-drawer class="bg-blue-3" v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header class="text-h6 text-blue-10">
          Contents
        </q-item-label>

        <ContentsLink
          v-for="link in contentsList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
      <q-list>
        <q-item-label header class="text-h6 text-blue-10"> Links </q-item-label>

        <EssentialLink
          v-for="link in linkList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container class="bg-cyan-1">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import EssentialLink from 'components/EssentialLink.vue';
import ContentsLink from 'components/ContentsLink.vue';
const contentsList = [
  {
    title: 'Home',
    caption: '',
    icon: 'home',
    link: '/',
  },

  {
    title: 'Profile',
    caption: '',
    icon: 'badge',
    link: 'profile',
  },

  {
    title: '工事中',
    caption: '',
    icon: 'construction',
    link: '404',
  },
];

const linksList = [
  {
    title: 'AtCoder',
    caption: 'deuteridayo',
    icon: 'trending_up',
    link: 'https://atcoder.jp/users/deuteridayo',
  },
  {
    title: 'Twitter',
    caption: '@deuteridayodayo',
    icon: 'img:icons/twitter.svg',
    link: 'https://twitter.com/deuteridayodayo',
  },

  {
    title: 'Github',
    caption: 'github.com/deuteridayo',
    icon: 'img:icons/github-mark.svg',
    link: 'https://github.com/deuteridayo',
  },

  {
    title: 'Wish List',
    caption: 'ほしいもの',
    icon: 'shopping_cart',
    link: 'https://www.amazon.co.jp/hz/wishlist/ls/2F5Z4J449A4KJ?ref_=wl_share',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
    ContentsLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      linkList: linksList,
      contentsList: contentsList,
      leftDrawerOpen,

      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
