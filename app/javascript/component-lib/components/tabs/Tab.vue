<template>
  <div v-show="isActive" role="tabpanel" :id="id" :aria-labelledby="triggerId" class="tab">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "tab",
  props: {
    id: {
      required: true,
      type: String
    },
    title: {
      required: true,
      type: String
    }
  },
  data() {
    return {
      isActive: false
    }
  },

  computed: {
    triggerId () {
      return 'tab-trigger-' + this.id
    }
  }
}
</script>