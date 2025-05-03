<template>
  <div class="flex h-screen bg-secondary">
    <Sidebar :isOpen="isSidebarOpen" :hideSidebarBtn="hideSidebarBtn" :closeSidebar="closeSidebar" @toggle="isSidebarOpen = !isSidebarOpen" />

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
const hideSidebarBtn = ref(false)

const handleResize = () => {
  if (window.innerWidth >= 769) {
    isSidebarOpen.value = true
    hideSidebarBtn.value = true
  } else {
    isSidebarOpen.value = false
    hideSidebarBtn.value = false
  }
}

onMounted(() => {
  handleResize()

  window.addEventListener('resize', handleResize)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize)
})
</script>
