<template>
	<div v-if="!showFullVideo" id="SideNav" class="flex z-40 items-center w-[120px] h-screen bg-black relative">
      <img class="absolute top-4 w-[35px] mt-10 ml-10" src="/images/netflix-logo.png" />
      <div>
        <div class="py-2 mx-10 my-6">
          <Magnify fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
        <div class="py-2 mx-10 my-6 border-b-4 border-b-red-500">
          <HomeOutline fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
        <div class="py-2 mx-10 my-6">
          <TrendingUp fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
        <div class="py-2 mx-10 my-6">
          <Television fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
        <div class="py-2 mx-10 my-6">
          <MovieOutline fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
        <div class="py-2 mx-10 my-6">
          <Plus fillColor="#fff" :size="40" class="cursor-pointer" />
        </div>
      </div>
    </div>
</template>

<script setup>
	import Magnify from 'vue-material-design-icons/Magnify.vue';
	import HomeOutline from 'vue-material-design-icons/HomeOutline.vue';
	import TrendingUp from 'vue-material-design-icons/TrendingUp.vue';
	import Television from 'vue-material-design-icons/Television.vue';
	import MovieOutline from 'vue-material-design-icons/MovieOutline.vue';
	import Plus from 'vue-material-design-icons/Plus.vue';

	import { useMovieStore } from '../stores/movie';
	import { storeToRefs } from 'pinia';

	const useMovie = useMovieStore();
	const { showFullVideo } = storeToRefs(useMovie);
</script>

<style lang="scss" scoped>

</style>