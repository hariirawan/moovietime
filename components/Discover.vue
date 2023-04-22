<template>
  <div class="relative pb-[115px]">
    <div class="h-[333px] absolute left-0 right-0 bg-white bg-opacity-5"></div>
    <div class="max-w-7xl mx-auto relative pt-[89px]">
      <div class="flex flex-row justify-between items-center">
        <div>
          <div class="w-[112px] h-[6px] bg-red-500"></div>
          <h6 class="mt-[12px] text-white">Discover Movies</h6>
        </div>
        <ul class="flex flex-row space-x-[21px]">
          <li class="btn-sort active">Popularity</li>
          <li class="btn-sort">Release Date</li>
        </ul>
      </div>

      <div class="grid grid-cols-5 gap-[25px] pt-[43px]">
        <div v-for="(item, index) in data" :key="index">
            <card-movie :id="index" :name="item.name" :year="item.year" :image="item.image" :rating="item.rating"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  const {data} = useListMovies();

</script>

<style>
.btn-sort {
  @apply rounded-full px-4 py-[6px] text-white text-xs bg-slate-950;
}

.active {
  @apply bg-red-500;
}
</style>
