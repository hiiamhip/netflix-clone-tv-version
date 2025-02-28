<template>
  <div
    class="fixed flex z-20 top-0 right-0 w-full h-[50%] bg-black pl-[120px] bg-clip-border"
  >
    <div
      class="absolute z-30 h-[600px] left-[120px] w-[77%] right-0 top-0 bg-gradient-to-r from-black via-black"
    ></div>
    <MovieDetails v-if="movie" :movie="movie" />
    <video
      v-if="movie"
      :src="'/videos/' + movie.name + '.mp4'"
      autoplay
      loop
      muted
      class="absolute z-0 h-[600px] right-0 top-0"
    ></video>
  </div>
</template>
  
<script setup>
  import { onMounted } from 'vue';

  import movies from "../movies.json";

	import MovieDetails from '@/components/MovieDetails.vue'

	import { useMovieStore } from '../stores/movie';
	import { storeToRefs } from 'pinia';

	const useMovie = useMovieStore();
	const { movie } = storeToRefs(useMovie);

  onMounted(() => {
    setTimeout(() => movie.value = movies[0][0], 10)
  })


</script>

<style lang="scss" scoped></style>
