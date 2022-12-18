<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  no: {
    default: 1,
  },
})

const no = ref(props.no)
</script>

<template>
  <a href="../9" class=""><sup>[{{no}}]</sup></a>
</template>
