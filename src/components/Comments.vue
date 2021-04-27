<template>
  <div
    class="fixed inset-0 bg-red-700 bg-center bg-cover"
    style="
      background-image: url('https://via.placeholder.com/1920x1080.png?text=MoviesDB+Background+Image');
    "
  >
    <button @click="emit('close')" class="absolute text-gray-400 right-4 top-4">
      <ant-design:close-circle-twotone
        class="w-11 h-11 filter drop-shadow-xl"
      />
    </button>
    <div class="inline-block px-3 py-3 mt-10">
      <h1
        class="text-5xl font-semibold tracking-wide uppercase text-gray-100 filter drop-shadow-xl"
      >
        movie.title
      </h1>
    </div>
    <div
      class="flex flex-col items-center py-3 space-y-3 overflow-y-scroll h-5/6"
    >
      <div
        v-for="(n, index) in 3"
        :key="index"
        class="w-1/2 px-3 py-1 text-left rounded bg-gray-100"
      >
        Comment
        <p class="mt-3 ml-auto text-xs text-right">User</p>
      </div>
      <input
        type="text"
        name=""
        id=""
        placeholder="New Comment"
        class="w-1/2 rounded bg-gray-100"
      />
    </div>
  </div>
</template>

<script setup>
import { defineEmit } from 'vue'

const emit = defineEmit(['close'])
</script>
