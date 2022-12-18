<template>
  <div class="h-[82%]">
    <div class="terminal">
      <div class="header">
        <div></div>
        <div></div>
        <div></div>
      </div>
      <slot />
    </div>
  </div>
</template>

<style scoped lang="postcss">
.terminal {
  @apply w-full h-full p-3 bg-blue-gray-900 rounded-lg text-base text-warm-gray-300 overflow-scroll;
  font-family: "Fira Code", "Noto Sans JP";

  .header {
    @apply w-full h-7 flex gap-2;
    & > div {
      @apply w-3 h-3 rounded-full
    }
    & > div:nth-child(1) {
      @apply bg-[#ff5e56]
    }
    & > div:nth-child(2) {
      @apply bg-[#ffbc2e]
    }
    & > div:nth-child(3) {
      @apply bg-[#28c840]
    }
  }
}
</style>
