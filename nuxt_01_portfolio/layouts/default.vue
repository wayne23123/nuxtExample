<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center mt-5">
      <div>
        <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200"
          >Wayne</NuxtLink
        >
      </div>

      <!-- 3-18 拆到 components 裡的 menu 去
      <nav class="font-mono">
        <ul class="flex space-x-4">
          <li>
            <NuxtLink to="/">main</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">about</NuxtLink>
          </li>
        </ul>
      </nav> -->

      <!-- 3-18 改完後用 Menu -->
      <Menu />
    </header>

    <!-- <slot /> -->

    <main class="p-2">
      <slot />
    </main>
  </div>
</template>

<script>
// /docs/getting-started/seo-meta#dynamic-title
useHead({
  titleTemplate: '%s - wayne',
  // %s -> replaced by the individual title of every page
  link: [
    {
      rel: 'preconnect',
      href: 'https://fonts.googleapis.com',
    },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
      crossorigin: '',
    },
  ],
  // /docs/getting-started/seo-meta#external-css
});
</script>

<style>
body {
  font-family: 'Roboto';
}
</style>
