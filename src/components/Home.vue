<template>
  <div class="container grid gap-3 mx-auto my-3 text-center lg:grid-cols-2">
    <Card v-for="(n, index) in 10" :key="index" />
  </div>
  <div class="flex items-center justify-center mb-3 space-x-3">
    <div>
      <button class="px-3 py-1 bg-gray-200 rounded">Prev</button>
    </div>
    <div>
      <p class="px-3 text-gray-300">Page 1 of 3</p>
    </div>
    <div>
      <button class="px-3 py-1 bg-gray-200 rounded">Next</button>
    </div>
  </div>
</template>
