<template>
  <q-layout view="lHh Lpr lFf" class="layout-header">
    <q-header elevated class="header text-black">
      <q-toolbar class="toolbar">
        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      class="drawer"
      content-class="bg-white"
    >
      <q-list class="list">
        <q-item-label
          header
          class="text-grey-8"
        >
          <q-img
            src="~assets/logo.png"
            spinner-color="white"
            class="logo"
            />
        </q-item-label>
      </q-list>
      <q-list
        v-for="(nav, index) in drawerList"
        :key="nav.header"
      >
        <hr class="list-hr" v-if="index !== 0">
        <NavGroup
            :header="nav.header"
            :links="nav.links"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import NavGroup from 'src/components/NavGroup.vue'

const linksData = [
  {
    header: 'MAIN',
    links: [
        {
            title: 'Dashboard',
            icon: 'las la-cog',
        }
    ]
  },
  {
    header: 'MANAGE LISTINGS',
    links: [
        {
            title: 'Add New',
            icon: 'las la-home',
        },
        {
            title: 'My Properties',
            icon: 'las la-house-damage',
        },
        {
            title: 'My Favorites',
            icon: 'lar la-heart',
        },
        {
            title: 'Save Search',
            icon: 'las la-warehouse',
        },
        {
            title: 'Reviews',
            icon: 'las la-comment-dots',
        },
        {
            title: 'Invoice',
            icon: 'las la-file-invoice',
        }
    ]
  },
  {
    header: 'MANAGE ACCOUNT',
    links: [
        {
            title: 'My Package',
            icon: 'las la-box',
            isActive: true,
        },
        {
            title: 'My Profile',
            icon: 'las la-user-alt',
        },
        {
            title: 'Logout',
            icon: 'las la-sign-out-alt',
        }
    ]
  },
];

export default {
  name: 'MainLayout',
  components: { NavGroup },
  data () {
    return {
      leftDrawerOpen: false,
      drawerList: linksData
    }
  }
}
</script>
