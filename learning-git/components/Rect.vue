<!--

Simple Arrow

<arrow x1="10" y1="20" x2="100" y2="200" color="green" width="3" />

<arrow v-bind="{ x1:10, y1:10, x2:200, y2:200 }"/>

-->

<script setup lang="ts">

defineProps<{
  x: number | string
  y: number | string
  width?: number | string
  height?: number | string
  color?: string
  strokeWidth: number | string
}>()

</script>

<template>
  <svg
    class="absolute left-0 top-0 pointer-events-none"
    width="100%"
    height="100%"
  >
    <rect 
      :x="+x"
      :y="+y"
      :width="width || 50"
      :height="height || 50"
      :stroke="color || 'currentColor'"
      :fill-opacity="0"
      :stroke-width="strokeWidth || 4"
    />
  </svg>
</template>