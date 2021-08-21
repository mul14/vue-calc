<script setup>
  import { ref, reactive } from 'vue';
  import Output from './Output.vue'
  import Button from './Button.vue'

  let output = ref('');

  const buttons = reactive([
    ["C"],
    [7, 8, 9, "/"],
    [4, 5, 6, "-"],
    [1, 2, 3, "+"],
    [0, '00', ".", "="],
  ]);

  const calc = v => {
    if (v === "C") {
      output.value = "";
    } else if (v === "=") {
      if (output.value.match(/[0-9=]$/)) {
        output.value = eval(output.value);
      }
    } else {
      output.value += String(v);
    }
  }
</script>

<template>
  <div class="flex items-center justify-center h-screen bg-gray-100">
    <div class="max-w-sm mx-auto bg-white p-4 rounded-lg shadow space-y-2">
      <Output :value="output" />
      <div v-for="(button, index) in buttons" :key="index" class="flex space-x-2">
        <div v-for="(btn, idx) in button" :key="idx" class="">
          <Button :value="btn" @click="calc(btn)" v-if="btn !== null"/>
        </div>
      </div>
    </div>
  </div>
</template>
