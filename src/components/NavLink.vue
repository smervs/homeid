<template>
  <q-item
    clickable
    tag="a"
    target="_blank"
    class="list-item"
    :class="isActive ? 'active' : ''"
  >
    <q-item-section
      v-if="icon"
      avatar
      class="section"
    >
      <q-icon :name="icon" class="list-item-icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: 'NavLink',
  props: {
    title: {
      type: String,
      required: true
    },

    icon: {
      type: String,
      default: ''
    },

    isActive: {
      type: Boolean,
      default: false
    }
  }
}
</script>
