<template>
  <div class="flex h-screen bg-secondary">
    <Sidebar :isOpen="isSidebarOpen" :closeSidebar="closeSidebar" @toggle="isSidebarOpen = !isSidebarOpen" />

    <div class="flex-1 flex flex-col overflow-hidden transition-all duration-300 ease-in-out" :class="{ 'md:ml-64': isSidebarOpen }">
      <Header :isSidebarOpen="isSidebarOpen" @toggleSidebar="isSidebarOpen = !isSidebarOpen" />
      <main class="flex-1 overflow-y-auto px-10">
        <slot />
      </main>
    </div>
  </div>
</template>

<script setup lang="ts">
const isSidebarOpen = ref(false)
const closeSidebar = () => isSidebarOpen.value = false
</script>
