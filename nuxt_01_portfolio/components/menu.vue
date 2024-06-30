<template>
  <nav class="font-mono">
    <ul class="flex space-x-4">
      <li>
        <NuxtLink to="/" class="link">main</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about">about</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/projects">projects</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.link {
  @apply p-1 hover:bg-gray-400;
}
</style>
