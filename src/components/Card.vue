<template>
  <div class="flex max-w-full">
    <img
      :src="`${posterBaseURL}${movie.poster_path}`"
      :alt="`Poster of ${movie.title}`"
    />
    <div
      class="flex flex-col justify-between p-3 leading-normal border-b border-l border-r rounded-b bg-gray-200 border-gray-500 lg:border-l-0 lg:border-t lg:border-gray-500 lg:rounded-b-none lg:rounded-r"
    >
      <div class="mb-9">
        <div class="mb-3 text-2xl font-semibold text-red-700 tracking-wider">
          {{ movie.title }}
        </div>
        <p class="text-amber-600 line-clamp-6">
          {{ movie.overview }}
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
  <Comments v-if="value" @close="toggle" :movie="movie" />
</template>

<script setup>
import { defineProps } from 'vue'
import { useToggle } from '@vueuse/core'
import { posterBaseURL } from '~/helpers/useMovies'

const [value, toggle] = useToggle(false)

const props = defineProps({
  movie: {
    type: Object,
    default: () => {
      return {
        title: '',
        overview: '',
        poster_path: '',
      }
    },
  },
})
</script>
