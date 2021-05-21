<template>
  <q-list class="list">
    <q-item-label
        header
        class="text-grey-6"
    >
        {{ header }}
    </q-item-label>
    <NavLink
        v-for="link in links"
        :key="link.title"
        v-bind="link"
    />
  </q-list>
</template>

<script>
import NavLink from './NavLink.vue'

export default {
  name: 'NavGroup',
  props: {
    header: {
      type: String,
      required: true
    },

    links: {
      type: Array,
      default: () => []
    },
  },
  components: {
      NavLink
  }
}
</script>
