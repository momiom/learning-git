<script setup lang="ts">
import { ref } from 'vue'

const props = withDefaults(defineProps<{
  underline: boolean,
  arrow: boolean,
  click: boolean
}>(), {
  underline: true,
  arrow: true,
  click: true
})

const underline = ref(props.underline)
const arrow = ref(props.arrow)
const click = ref(props.click)
</script>

<template>
  <div v-if="click" class="mt-5 text-center" v-click>
    <material-symbols-arrow-downward v-show="arrow" class="text-2xl"/>
    <h2 class="text-center text-2xl mt-2">
      <template v-if="underline">
        <span class="underline underline-offset-4 decoration-blue-800/50">
          <slot></slot>
        </span>
      </template>
      <template v-else>
        <slot></slot>
      </template>
    </h2>

    <div class="text-lg">
      <slot name="body"></slot>
    </div>
  </div>

  <div v-else class="mt-5 text-center">
    <material-symbols-arrow-downward v-show="arrow" class="text-2xl"/>
    <h2 class="text-center text-2xl mt-2">
      <template v-if="underline">
        <span class="underline underline-offset-4 decoration-blue-800/50">
          <slot></slot>
        </span>
      </template>
      <template v-else>
        <slot></slot>
      </template>
    </h2>

    <div class="text-lg">
      <slot name="body"></slot>
    </div>
  </div>
</template>

<style scoped>
h2 {
  @apply mt-4 mb-4;
}
</style>
