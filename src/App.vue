<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const x = ref(0)
const y = ref(0)

function update(event) {
  x.value = event.pageX
  y.value = event.pageY
}

//We bind the mousemove event to our function to update the position
onMounted(() => window.addEventListener('mousemove', update))


onUnmounted(() => window.removeEventListener('mousemove', update))
</script>

<template>
  Mouse position is at: {{ x }}, {{ y }}
  <!-- The router-view here indicate the result of the computed routed component will be inserted here -->
  <router-view>
  </router-view>
</template>
