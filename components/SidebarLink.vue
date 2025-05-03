<template>
  <button
    class="flex items-center w-full text-left text-gray-600 font-semibold px-3 py-2 rounded-lg transition-colors duration-200
           hover:bg-primary/10 hover:text-primary cursor-pointer"
    :class="{ 'bg-primary hover:!bg-primary text-white hover:!text-white': active }"
  >
    <Icon :name="icon" class="size-6" />
    <span class="ml-3 flex-1">{{ text }}</span>
    <span v-if="hasNotification" class="ml-auto size-4 bg-primary text-white text-[0.60rem] text-center rounded-full">{{count}}</span>
  </button>
</template>

<script setup lang="ts">
defineProps<{
  icon: string
  text: string
  active?: boolean
  hasNotification?: boolean
  count?: number
}>()
</script>
