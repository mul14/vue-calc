<script setup>
  import { defineProps } from 'vue'
  defineProps(['value'])
</script>

<template>
  <button class="w-20 h-20 bg-gray-200 hover:bg-gray-300 text-xl rounded">
    {{ value }}
  </button>
</template>
