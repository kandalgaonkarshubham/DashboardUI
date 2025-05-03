<template>
  <div class="bg-white rounded-2xl shadow-lg p-8">
    <h2 class="text-xl font-semibold mb-6 text-gray-800">Monthly Revenue</h2>
    <div class="text-3xl font-extrabold mb-2 text-gray-900">$15,000</div>

    <div class="flex items-end justify-between h-40 mt-8">
      <template v-for="(month, idx) in months" :key="month.label">
        <div class="flex flex-col items-center w-10 relative">
          <div
            :class="[
              'w-full rounded-t-md transition-all duration-300',
              idx === 5 ? 'bg-primary h-32 shadow-lg relative' : 'bg-gray-200 h-16'
            ]"
          >
            <span v-if="idx === 5" class="absolute -top-8 left-1/2 -translate-x-1/2 bg-gray-900 text-white text-xs font-bold px-3 py-1 rounded shadow-lg z-10">$15,000</span>
          </div>
          <span class="mt-3 text-xs text-gray-500 font-semibold">{{ month.label }}</span>
        </div>
      </template>
    </div>
  </div>
</template>

<script setup lang="ts">
const months = [
  { label: 'Mar' },
  { label: 'Apr' },
  { label: 'May' },
  { label: 'Jun' },
  { label: 'Jul' },
  { label: 'Aug' },
  { label: 'Sep' },
  { label: 'Oct' },
  { label: 'Nov' }
]
</script>
