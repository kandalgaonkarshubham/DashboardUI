<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
    <div
      v-for="(card, index) in cards"
      :key="index"
      class="bg-white rounded-xl p-4 flex items-center gap-4"
    >
      <Icon :name="card.icon" class="size-14" />
      <div class="flex flex-col">
        <span class="text-gray-500 font-semibold text-sm">{{ card.title }}</span>
        <span class="text-3xl font-semibold">{{ card.value }}</span>
        <p
          :class="[
            'w-fit flex items-center justify-center rounded-lg p-1 mt-1',
            card.profit ? 'text-green-500 bg-green-500/20' : 'text-red-500 bg-red-500/20'
          ]"
        >
          <span class="text-sm font-bold">{{ card.change }}</span>
          <Icon v-if="card.profit" name="line-md:arrow-small-right" class="size-5 -rotate-45 mt-0.5" />
          <Icon v-else name="line-md:arrow-small-right" class="size-5 rotate-45 mt-0.5" />
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
const cards = [
  { title: 'Total Revenue', value: '$216k', change: '+341', icon: 'fluent-color:board-28', profit: true },
  { title: 'Invoices', value: '2,221', change: '+121', icon: 'fluent-color:receipt-28', profit: true },
  { title: 'Clients', value: '1,423', change: '+93', icon: 'fluent-color:people-community-28', profit: true },
  { title: 'Loyalty', value: '78%', change: '-1%', icon: 'fluent-color:person-heart-28', profit: false },
];
</script>
