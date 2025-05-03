<template>
  <div class="flex flex-col gap-4">
    <Analytics />

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-4">
      <div class="lg:col-span-2">
        <MonthlyRevenue />
      </div>
      <div>
        <AnnouncementCard />
      </div>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-4">
      <div>
        <RecentActivity />
      </div>
      <div class="lg:col-span-2">
        <InvoiceTable />
      </div>
    </div>
  </div>
</template>
