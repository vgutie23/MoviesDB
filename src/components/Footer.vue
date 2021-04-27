<template>
  <footer class="bg-gray-900">
    <div
      class="container flex items-center justify-between px-2 py-1 mx-auto space-x-3 space-y-2 text-gray-500"
    >
      <div class="text-xs">
        Icons made by
        <a
          href="https://www.freepik.com"
          title="Freepik"
          class="text-orange-600 hover:underline hover:text-orange-400"
          >Freepik</a
        >
        from
        <a
          href="https://www.flaticon.com/"
          title="Flaticon"
          class="text-orange-600 hover:underline hover:text-orange-400"
          >www.flaticon.com</a
        >
      </div>
      <img :src="tmdbLogo" alt="TMDB Logo" class="w-10 h-10" />
    </div>
  </footer>
</template>

<script setup>
import tmdbLogo from '~/assets/themoviedblogo.svg'
</script>
