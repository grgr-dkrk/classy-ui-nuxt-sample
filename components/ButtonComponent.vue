<template>
  <button
    :class="style"
    :aria-pressed="isActive ? 'true' : 'false'"
    @click="toggleActive"
  >
    Sample Button
  </button>
</template>

<script lang="ts">
import Vue from 'vue'
import { ref, computed } from '@vue/composition-api'
import { styleButton } from './styles' // classy-ui

export default Vue.extend({
  setup() {
    const isActive = ref(false)
    const style = computed(() => styleButton({ isActive: isActive.value })) // style
    function toggleActive() {
      isActive.value = !isActive.value
    }
    return {
      isActive,
      style,
      toggleActive
    }
  }
})
</script>
