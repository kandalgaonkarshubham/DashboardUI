<template>
  <div class="bg-white rounded-2xl shadow-lg p-8">
    <h2 class="text-xl font-semibold mb-6 text-gray-800">Monthly Revenue</h2>
    <div class="text-3xl font-extrabold mb-2 text-gray-900">$15,000</div>

    <div class="flex items-end justify-between h-40 mt-8">
      <Bar
        :data="chartData"
        :options="chartOptions"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { Bar } from 'vue-chartjs'

const chartData = ref({
  labels: ['Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov'],
  datasets: [
    {
      label: '',
      backgroundColor: '#e6e9ee',
      hoverBackgroundColor: '#055ffc',
      borderRadius: 8,
      borderSkipped: false,
      data: [2000, 3500, 1500, 2700, 3000, 4200, 3100, 3900, 2500],
    },
  ],
})

const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      display: false,
    },
    tooltip: {
      backgroundColor: '#1f2937',
      cornerRadius: 8,
      padding: 10,
      bodyFont: {
        size: 14,
        weight: 'bold',
      },
      displayColors: false,
      callbacks: {
        title: () => '',
        label: (context: any) => {
          return `$${context.raw}`
        },
      },
    },
  },
  scales: {
    y: {
      grid: {
        display: false,
        drawBorder: false,
      },
      ticks: {
        display: false,
      },
      border: {
        display: false,
      },
    },
    x: {
      grid: {
        display: false,
        drawBorder: false,
      },
      ticks: {
        font: {
          weight: '400',
        },
      },
      border: {
        display: false,
      },
    },
  },
})
</script>
