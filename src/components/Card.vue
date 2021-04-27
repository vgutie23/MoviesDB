<template>
  <div class="flex max-w-full">
    <img src="https://via.placeholder.com/200x300.png" alt="Movie Poster" />
    <div
      class="flex flex-col justify-between p-3 leading-normal border-b border-l border-r rounded-b bg-gray-200 border-gray-500 lg:border-l-0 lg:border-t lg:border-gray-500 lg:rounded-b-none lg:rounded-r"
    >
      <div class="mb-9">
        <div class="mb-3 text-2xl font-semibold text-red-700 tracking-wider">
          movie.title
        </div>
        <p class="text-amber-600 line-clamp-6">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusamus
          modi harum quam porro eaque, totam omnis quod soluta, ab ex saepe
          consequuntur quas voluptatem ea asperiores dignissimos minus
          distinctio sed. Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Perferendis molestias assumenda totam repudiandae libero
          mollitia consectetur iusto maiores nobis. Magnam deleniti quos debitis
          similique dolor alias inventore labore error ipsum.
        </p>
      </div>
      <div class="flex items-start justify-end">
        <div class="flex flex-col items-center">
          <button class="text-gray-400 hover:text-red-700">
            <bi:suit-heart-fill class="w-6 h-6" />
            <span>3</span>
          </button>
        </div>
        <div class="flex flex-col items-center">
          <button
            @click="toggle"
            class="text-coolGray-400 hover:text-amber-600"
          >
            <ic:round-mode-comment class="w-6 h-6" />
          </button>
        </div>
      </div>
    </div>
  </div>
  <Comments v-if="value" @close="toggle" />
</template>

<script setup>
import { useToggle } from '@vueuse/core'

const [value, toggle] = useToggle(false)
</script>
