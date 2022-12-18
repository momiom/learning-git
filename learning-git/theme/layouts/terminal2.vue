<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layoutHelper'

const props = defineProps({
  background: {
    default: '',
  },
})

const style = computed(() => handleBackground(props.background, true))
</script>

<template>
  <div class="slidev-layout default terminal" :style="style">
    <slot />
    <div class="grid grid-cols-[1.5fr,1fr] gap-4 h-full">
      <div>
        <slot name="left" />
      </div>
      <div>
        <slot name="right" />
      </div>
    </div>
  </div>
</template>
