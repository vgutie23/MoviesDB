<template>
  <div
    class="fixed inset-0 bg-red-700 bg-center bg-cover"
    :style="`
      background-image: url('${bgBaseURL}${movie.backdrop_path}');
    `"
  >
    <button @click="emit('close')" class="absolute text-gray-200 right-4 top-4">
      <ant-design:close-circle-twotone
        class="w-11 h-11 filter drop-shadow-xl"
      />
    </button>
    <div class="inline-block px-3 py-3 mt-10">
      <h1
        class="text-5xl font-semibold tracking-wide uppercase text-gray-100 filter drop-shadow-xl"
      >
        {{ movie.title }}
      </h1>
    </div>
    <div
      class="flex flex-col items-center py-3 space-y-3 overflow-y-scroll h-5/6"
    >
      <div
        v-for="({ text, userName }, index) in comments"
        :key="index"
        class="w-1/2 px-3 py-1 text-left rounded bg-gray-100"
      >
        {{ text }}
        <p class="mt-3 ml-auto text-xs text-right">{{ userName }}</p>
      </div>
      <input
        type="text"
        name=""
        id=""
        placeholder="New Comment"
        class="w-1/2 rounded bg-gray-100"
        v-model="newComment"
        @change="add"
      />
    </div>
  </div>
</template>

<script setup>
import { defineEmit, defineProps, ref } from 'vue'
import { bgBaseURL } from '~/helpers/useMovies'
import { database } from '~/helpers/useFirebase'

const newComment = ref('')
const emit = defineEmit(['close'])

const props = defineProps({
  movie: {
    type: Object,
    default: () => {
      return {
        title: '',
        backdrop_path: '',
      }
    },
  },
})

const { comments, addComment } = database(props.movie.id)

const add = () => {
  addComment(newComment.value)
  newComment.value = ''
}
</script>
