<template>
  <div class="flex items-center justify-center mb-3 space-x-3">
    <div>
      <button @click="prevPage" class="px-3 py-1 bg-gray-200 rounded">
        Prev
      </button>
    </div>
    <div>
      <p class="px-3 text-gray-300">Page {{ page }} of {{ pages }}</p>
    </div>
    <div>
      <button @click="nextPage" class="px-3 py-1 bg-gray-200 rounded">
        Next
      </button>
    </div>
  </div>
</template>

<script setup>
import { page, pages, nextPage, prevPage } from '~/helpers/useMovies'
</script>
