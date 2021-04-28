<template>
  <nav class="bg-gray-900">
    <div class="container flex items-center justify-between mx-auto">
      <div class="flex items-center space-x-3">
        <fxemoji:moviecamera class="w-14 h-14" />
        <p
          class="text-3xl tracking-wide text-transparent font-light bg-clip-text bg-gradient-to-r from-red-600 to-orange-400"
        >
          Extensive<span class="font-semibold">MoviesDB</span>
        </p>
      </div>
      <div>
        <div v-if="isAuthenticated" class="flex items-center space-x-3">
          <p class="text-gray-200">Welcome {{ user?.displayName }}</p>
          <button
            @click="out"
            class="px-6 py-2 font-semibold bg-orange-600 rounded-full focus:ring-orange-800 focus:ring-3 focus:outline-none text-gray-200 hover:bg-orange-700"
          >
            Logout
          </button>
        </div>
        <div v-else>
          <button
            @click="signIn"
            class="px-6 py-2 font-semibold bg-amber-500 rounded-full focus:ring-amber-700 focus:ring-3 focus:outline-none text-gray-200 hover:bg-amber-600"
          >
            Login
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { authentication } from '~/helpers/useFirebase'
import { movies, page } from '~/helpers/useMovies'

const { signIn, signOut, isAuthenticated, user } = authentication()

const out = () => {
  signOut()
  page.value = 1
  movies.value = []
}
</script>
