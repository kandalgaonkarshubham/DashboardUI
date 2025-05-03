<template>
  <div class="bg-white rounded-2xl shadow-lg p-8">
    <h2 class="text-xl font-bold mb-6 text-gray-900">Recent Invoices</h2>
    <div class="overflow-x-auto">
      <table class="w-full text-sm text-left">
        <thead class="text-gray-400 uppercase text-xs border-b">
          <tr>
            <th class="py-3 px-4 font-semibold">No</th>
            <th class="py-3 px-4 font-semibold">Date Created</th>
            <th class="py-3 px-4 font-semibold">Client</th>
            <th class="py-3 px-4 font-semibold">Amount</th>
            <th class="py-3 px-4 font-semibold">Status</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(invoice, index) in invoices"
            :key="index"
            class="hover:bg-gray-50 border-t transition"
          >
            <td class="py-3 px-4 font-medium text-gray-700">{{ invoice.no }}</td>
            <td class="py-3 px-4 text-gray-500">{{ invoice.date }}</td>
            <td class="py-3 px-4 text-gray-700">{{ invoice.client }}</td>
            <td class="py-3 px-4 font-semibold text-gray-900">$ {{ invoice.amount }}</td>
            <td class="py-3 px-4">
              <span 
                :class="[
                  'px-3 py-1 rounded-full uppercase text-xs font-bold',
                  invoice.status === 'overdue' ? 'text-red-600 bg-red-100' : 'text-green-600 bg-green-100',
                ]"
              >
                {{ invoice.status }}
              </span>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup lang="ts">
const invoices = [
  { no: 'PQ-4491C', date: '3 July, 2026', client: 'Danielle Padilla', amount: 2450, status: 'paid' },
  { no: 'IN-8923A', date: '15 June, 2026', client: 'Carlos Mendez', amount: 1375, status: 'overdue' },
  { no: 'IN-7742B', date: '29 June, 2026', client: 'Aisha Sharma', amount: 1980, status: 'paid' },
  { no: 'IN-6654D', date: '10 July, 2026', client: 'Ryan Lee', amount: 3050, status: 'overdue' },
  { no: 'IN-5563E', date: '1 July, 2026', client: 'Meera Nair', amount: 990, status: 'paid' },
  { no: 'IN-1145F', date: '20 June, 2026', client: 'Liam Turner', amount: 1650, status: 'overdue' },
  { no: 'IN-7733G', date: '7 July, 2026', client: 'Sofia Verma', amount: 2200, status: 'paid' },
  { no: 'IN-2244H', date: '5 July, 2026', client: 'John Doe', amount: 1780, status: 'paid' },
]

</script>
