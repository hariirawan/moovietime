<template>
  <div class="card-movie">
    <div class="relative">
      <span
        class="absolute right-0 top-0 py-[5px] px-[10px] bg-slate-700 bg-opacity-80 font-bold text-lg text-white"
        >{{ props.rating }}</span
      >
      <div class="card-movie-hover text-white">
        <div
          class="flex flex-row items-center font-semibold text-2xl space-x-[10px]"
        >
          <img src="/icons/Star.png" class="w-[32px] h-[32px]" />
          <div>{{ props.rating }}</div>
        </div>
        <div class="font-semibold text-lg">Action</div>
        <NuxtLink :to="'/movie/'+props.id">
          <button class="btn-view">View</button>
        </NuxtLink>
      </div>

      <img
        :src="props.image"
        class="h-[330px] object-fill w-full"
      />
    </div>
    <div class="font-semibold text-base text-white mt-[13px]">
      {{props.name}}
    </div>
    <div class="font-thin text-sm text-white">{{ props.year }}</div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps({
  id: Number,
  name:String,
  image:String,
  year:String,
  rating:String
});
</script>

<style>
.card-movie-hover {
  @apply opacity-0 absolute bg-slate-800 bg-opacity-80 left-0 right-0 bottom-0 top-0 flex flex-col justify-center items-center space-y-[48px] z-20;
}

.card-movie:hover .card-movie-hover {
  @apply opacity-100 ease-in duration-300 cursor-pointer;
}

.btn-view {
  @apply bg-red-500 py-[7px] px-[33px] rounded-full;
}
</style>
