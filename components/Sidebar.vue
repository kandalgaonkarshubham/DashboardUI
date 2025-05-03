<template>
  <aside
    :class="[
      'bg-secondary h-full shadow-lg md:shadow-none transition-transform duration-300 ease-in-out z-20 p-6',
      isOpen ? 'translate-x-0' : '-translate-x-full',
      'fixed md:fixed w-64'
    ]"
  >
    <div class="p-6 flex items-center justify-between gap-2">
      <h1 class="font-bold text-xl">Invo.</h1>
      <button v-if="isOpen" @click="closeSidebar" class="cursor-pointer">
        <Icon name="line-md:close-small" class="size-6 text-gray-500 mt-1" />
      </button>
    </div>
    <nav class="mt-6 space-y-4 px-4">
      <SidebarLink
        v-for="(link, index) in sidebarLinks"
        :key="index"
        v-bind="link"
      />
    </nav>

    <div class="absolute bottom-4 w-full px-4">
      <SidebarLink icon="duo-icons:dashboard" text="Log Out" />
    </div>
  </aside>
</template>

<script setup lang="ts">
defineProps<{
  isOpen: boolean
  closeSidebar: (e: MouseEvent) => void
}>()

const sidebarLinks = [
  { icon: 'duo-icons:building', text: 'Home', active: true },
  { icon: 'duo-icons:clipboard', text: 'Invoices' },
  { icon: 'duo-icons:user', text: 'Clients' },
  { icon: 'duo-icons:slideshow', text: 'Products' },
  { icon: 'duo-icons:message-2', text: 'Messages', hasNotification: true, count: 2 },
  { icon: 'duo-icons:settings', text: 'Settings' },
  { icon: 'duo-icons:alert-octagon', text: 'Help' }
]

</script>
