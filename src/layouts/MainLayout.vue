<template>
  <q-layout view="hHh lpr lFr">
    <q-header> <HeaderMenu></HeaderMenu> </q-header>

    <q-drawer
      v-model="drawerVisivel"
      bordered
      :mini="drawerMini"
      @mouseout="drawerMini = true"
      @mouseover="drawerMini = false"
    >
      <q-scroll-area class="fit">
        <DrawerMenu></DrawerMenu>
        <!-- <q-list>
          <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
          />
        </q-list> -->
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
// import EssentialLink from 'components/EssentialLink.vue';

//import components
import HeaderMenu from 'src/views/layouts/HeaderMenu.vue';
import DrawerMenu from 'src/views/layouts/DrawerMenu.vue';

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'home',
    link: 'https://quasar.dev',
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'assessment',
    link: 'https://github.com/quasarframework',
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'attach_money',
    link: 'https://chat.quasar.dev',
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'point_of_sale',
    link: 'https://forum.quasar.dev',
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'shopping_cart',
    link: 'https://twitter.quasar.dev',
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'tag_faces',
    link: 'https://facebook.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'contacts',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Produtos',
    caption: 'Community Quasar projects',
    icon: 'diamond',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'precision_manufacturing',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'interests',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'query_stats',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'desktop_windows',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Produtos',
    caption: 'Community Quasar projects',
    icon: 'diamond',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'precision_manufacturing',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'interests',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'query_stats',
    link: 'https://awesome.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'desktop_windows',
    link: 'https://awesome.quasar.dev',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink,
    HeaderMenu,
    DrawerMenu,
  },
  data() {
    return {
      drawerVisivel: true,
      drawerMini: true,
    };
  },
  methods: {
    toggleLeftDrawer() {
      this.drawerMini = !this.drawerMini;
    },
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
    };
  },
});
</script>
<style scoped>
.rounded-circle {
  border-radius: 50%;
  width: 40px;
  height: 40px;
  object-fit: cover;
}
</style>
