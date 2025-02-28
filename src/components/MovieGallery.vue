<template>
  <div
    class="fixed z-30 bottom-0 right-0 w-full h-[55%] pl-[120px] overflow-y-auto scrollbar-hidden"
  >
    <VideoCarousel
      class="pb-14 pt-14"
      category="Popular Movies"
      :movies="movies[0]"
    />
    <VideoCarousel class="pb-14" category="Horror Movies" :movies="movies[1]" />
    <VideoCarousel
      class="pb-32"
      category="Featured Movies"
      :movies="movies[2]"
    />
  </div>
</template>

<script setup>
	import movies from "../movies.json";
	import VideoCarousel from '@/components/VideoCarousel.vue';
</script>

<style scoped>
.scrollbar-hidden::-webkit-scrollbar {
  display: none;
}
.scrollbar-hidden {
  scrollbar-width: none;
}
</style>
