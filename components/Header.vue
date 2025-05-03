<template>
  <header class="!backdrop-blur-sm flex items-center justify-between gap-4 sticky top-0 z-10 p-10">
    <div class="flex-1 flex items-center justify-start gap-4 py-1.5">
      <button v-if="!isSidebarOpen" @click="$emit('toggleSidebar')">
        <Icon name="line-md:menu-fold-right" class="size-6 text-gray-500 mt-1" />
      </button>
      <div class="flex items-center justify-center gap-2">
        <Icon name="line-md:search" class="size-6 text-gray-500 scale-x-[-1]" />
        <input
          type="text"
          placeholder="Tap to search"
          class="w-full max-w-md rounded-md text-sm p-1 focus:outline-none placeholder:font-medium"
        />
      </div>
    </div>

    <div class="flex items-center gap-4">
      <div class="relative mt-1">
        <p class="absolute -top-1 -right-1 bg-primary text-white text-[0.60rem] text-center font-bold rounded-full size-4 p-0 m-0">2</p>
        <Icon name="duo-icons:bell" class="size-6" />
      </div>
      <div class="block md:hidden relative">
        <button @click="isProfileOpen = !isProfileOpen">
          <Icon name="line-md:menu" class="size-6 text-gray-500" />
        </button>
        <div v-if="isProfileOpen" class="w-40 absolute right-0 flex items-center justify-center gap-2 bg-white shadow-md rounded-md p-4 mt-2">
          <img src="https://randomuser.me/api/portraits/men/32.jpg" class="size-8 rounded-full" alt="User" />
          <div class="flex flex-col">
            <span class="font-bold text-sm">David Spade</span>
            <span class="text-xs font-bold text-gray-500">Sales Admin</span>
          </div>
        </div>
      </div>

      <div class="hidden md:flex items-center gap-4">
        <img src="https://randomuser.me/api/portraits/men/32.jpg" class="size-8 rounded-full" alt="User" />
        <div class="flex flex-col">
          <span class="font-bold text-sm">David Spade</span>
          <span class="text-xs font-bold text-gray-500">Sales Admin</span>
        </div>
      </div>
    </div>

  </header>
</template>

<script setup lang="ts">
defineProps({
  isSidebarOpen: Boolean
})

const isProfileOpen = ref(false);
</script>
