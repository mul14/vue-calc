<script setup>
  import { defineProps } from "vue";
  defineProps(["value"]);
</script>
  
<template>
  <div class="border text-3xl text-right h-16 px-2 flex items-center justify-end border rounded-lg bg-gradient-to-b from-gray-100 to-gray-50 shadow-inner">
    {{ value }}
  </div>
</template>
