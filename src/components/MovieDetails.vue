<template>
	<div v-if="movie" class="z-40 text-white w-[53%] p-20">
		<div class="text-[55px] font-semibold font-serif">{{ movie.name }}</div>
	</div>
</template>

<script setup>
	defineProps({ movie: Object })
</script>