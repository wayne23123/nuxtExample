<template>
  <p class="mb-10">my github project</p>

  <section v-if="pending">loading . . .</section>
  <section v-else-if="error">something went wrong</section>
  <section v-else>
    <ul class="grid grid-col-1 gap-4">
      <!-- <li
        v-for="repository in data"
        :key="repository.id"
        class="border border-gray-200 rounded-sm p-4 gover:bg-gray-100 font-mono"
      > -->
      <li
        v-for="repository in repos"
        :key="repository.id"
        class="border border-gray-200 rounded-sm p-4 gover:bg-gray-100 font-mono"
      >
        <a :href="repository.html_url" target="_blank">
          <div class="flex justify-between items-center text-sm">
            <div>{{ repository.name }}</div>
            <div>{{ repository.stargazers_count }} *</div>
          </div>
          <p class="text-sm">
            {{ repository.description }}
          </p>
        </a>
      </li>
    </ul>
  </section>
</template>

<script setup>
// console.log(await $fetch('https://api.github.com/users/wayne23123/repos'))
// server & client 會跑 2 次

const { error, pending, data } = await useFetch(
  'https://api.github.com/users/wayne23123/repos'
);

const repos = computed(() =>
  data.value
    .filter((item) => item.description)
    .sort((a, b) => b.stargazers_count - a.stargazers_count)
);

// [1,3,5].sort*=((a,b)=>{console.log(a,b,a-b); return a-b;})
// 3 1 2
// 5 3 2
// [1,3,5]

// [1,3,5].sort*=((a,b)=>{console.log(a,b,b-a); return b-a;})
// 3 1 -2
// 5 3 -2
// [5,3,1]
</script>
