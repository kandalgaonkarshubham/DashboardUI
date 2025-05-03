<template>
  <div class="bg-white rounded-2xl shadow-lg p-8 h-full">
    <h2 class="text-xl font-semibold mb-6 text-gray-800">Activities</h2>
    <ul class="space-y-8">
      <li v-for="(item, index) in activities" :key="index" class="flex items-center gap-4">
        <div class="bg-primary/10 text-primary rounded-full flex items-center justify-center w-12 h-12">
          <Icon name="fluent-color:alert-28" class="w-7 h-7" />
        </div>
        <div>
          <p class="font-semibold text-base text-gray-800">{{ item.title }}</p>
          <p class="text-gray-400 font-medium text-xs mt-1">{{ item.time }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
const activities = [
  { title: 'Invoice #1022 sent to Emily Stone', time: '2 hours ago' },
  { title: 'Payment received from Mike Patel', time: '5 hours ago' },
  { title: 'Client John Carter added', time: '1 day ago' }
]
</script>
