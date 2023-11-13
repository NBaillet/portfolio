<template>
  <div class="flex">
    <SummaryPanel class="w-3/12 max-w-md"/>
    <DetailPanel class="w-9/12"/>
  </div>
</template>

<script setup>
import SummaryPanel from './components/SummaryPanel.vue'
import DetailPanel from './components/DetailPanel.vue'

</script>

<style src="./assets/tailwind.css" />
<style>
html { 
  @apply h-full bg-stone-900 text-stone-300 font-mono;
}
</style>
