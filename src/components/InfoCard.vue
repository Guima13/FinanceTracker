<template>
  <div class="bg-gray-800 p-5 rounded-lg shadow-lg border border-teal-600/50 hover:bg-gray-700 transition duration-300">
    <div class="flex items-center justify-between">
      <div class="text-sm font-medium text-gray-400 uppercase">
        {{ title }}
      </div>
      <span class="text-2xl">{{ icon }}</span>
    </div>
    <div class="text-3xl font-bold text-teal-400 mt-1">
      {{ value }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'InfoCard',
  props: {
    title: {
      type: String,
      required: true
    },
    value: {
      type: [String, Number],
      required: true
    },
    icon: {
      type: String,
      default: '⭐'
    }
  }
}
</script>