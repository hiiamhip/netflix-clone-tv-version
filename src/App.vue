<script setup>

import SideNav from '@/components/SideNav.vue'
import MovieGallery from '@/components/MovieGallery.vue'
import FullVideo from '@/components/FullVideo.vue'
import MovieShowcase from '@/components/MovieShowcase.vue'


import { useMovieStore } from './stores/movie';
import { storeToRefs } from 'pinia';

const useMovie = useMovieStore();
const { showFullVideo } = storeToRefs(useMovie);

</script>

<template>
  <div class="fixed w-full h-screen bg-black">
    <div v-if="!showFullVideo">
      <SideNav />   
      <MovieShowcase />
      <MovieGallery />
      <div class="absolute z-20 h-[70%] left-[120px] w-[100%] right-0 bottom-0 bg-gradient-to-t from-black via-black"></div>
    </div>
    <FullVideo v-if="showFullVideo"/>
  </div>
</template>

<style scoped>

</style>
