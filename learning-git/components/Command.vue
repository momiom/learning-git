<script setup lang="ts">
import { ref } from 'vue'

const props = withDefaults(defineProps<{
  click: boolean
}>(), {
  click: true
})
const click = ref(props.click)
</script>

<template>
    <div v-if="click" class="command-block">
        <div v-click class="prompt-text">/what-is-git-workflow</div>
        <div class="line">
            <div v-after class="prompt">&gt;&nbsp;</div>
            <div v-click class="content">
                <slot name="command" />
            </div>
        </div>
        <div v-click class="result">
            <slot name="result" />
        </div>
    </div>

    <div v-else class="command-block">
        <div class="prompt-text">/what-is-git-workflow</div>
        <div class="line">
            <div v-after class="prompt">&gt;&nbsp;</div>
            <div class="content">
                <slot name="command" />
            </div>
        </div>
        <div class="result">
            <slot name="result" />
        </div>
    </div>
</template>

<style scoped lang="postcss">
.command-block {
    @apply ml-1 mb-4;

    .line {
        @apply flex gap-1;
    }

    .content {
        @apply w-full;
    }

    .result{
        @apply mt-1 pl-6 text-warm-gray-50;
        p {
            @apply m-0;
        }
    }
}
</style>
