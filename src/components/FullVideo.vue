<template>
  <div>
    <div
      @click="showFullVideo = false"
      class="absolute z-50 p-2 m-4 bg-white bg-opacity-50 rounded-full cursor-pointer"
    >
      <ChevronLeft :size="40" />
    </div>
    <video
      :src="'/videos/' + movie.name + '.mp4'"
      autoplay
      loop
      controls
      class="absolute z-0 w-[100vw] h-full object-fit"
    ></video>
  </div>
</template>

<script setup>
	import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';

	import { useMovieStore } from '../stores/movie';
	import { storeToRefs } from 'pinia';

	const useMovie = useMovieStore();
	const { movie, showFullVideo } = storeToRefs(useMovie);
</script>

<style lang="scss" scoped></style>
