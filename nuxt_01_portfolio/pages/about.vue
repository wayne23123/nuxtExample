<template>
  <div>about me</div>

  <div>
    <button @click="enableCustomLayout">Update layout</button>
  </div>
</template>

<script setup>
// definePageMeta({
//   layout: 'another',
// });

// layouts#changing-the-layout-dynamically
function enableCustomLayout() {
  setPageLayout('another');
}
</script>
