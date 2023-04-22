<template>
  <div class="relative pb-[115px]">
    <div class="h-[333px] absolute left-0 right-0 bg-white bg-opacity-5"></div>
    <div class="relative mx-auto max-w-7xl pt-[54px]">
      <div>
        <div class="w-[112px] h-[6px] bg-red-500"></div>
        <h6 class="text-4xl font-semibold text-white mt-[12px]">Movies</h6>
      </div>
      <div class="flex pt-[43px] space-x-[30px]">
        <div>
          <div
            class="w-[240px] bg-gradient-to-b from-mirage to-dark py-5 text-white rounded-lg"
          >
            <div class="pb-[18px] border-b border-b-slate-700 px-4">
              Sort Result By
            </div>
            <listbox />
            <div class="py-[18px] border-b border-b-slate-700 px-4">Genres</div>
            <ul class="space-y-2 px-4 py-[18px]">
              <li
                v-for="(item, idx) in genres"
                :key="idx"
                class="flex justify-between items-center"
              >
                <span class="font-normal text-sm">
                  {{ item.name }}
                </span>
                <nuxt-icon
                  :name="
                    item.isSelected ? 'admin/checkbox' : 'admin/uncheckbox'
                  "
                  filled
                />
              </li>
            </ul>
          </div>
        </div>
        <div class="flex-1">
          <div class="grid grid-cols-4 gap-[25px]">
            <div v-for="(item, index) in data" :key="index">
              <card-movie
                :id="index"
                :name="item.name"
                :year="item.year"
                :image="item.image"
                :rating="item.rating"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const { data } = useListMovies();
const genres = [
  { name: "action", isSelected: true },
  { name: "Adventure", isSelected: false },
  { name: "Animation", isSelected: false },
  { name: "Animation", isSelected: false },
  { name: "Comedy", isSelected: false },
  { name: "Crime", isSelected: false },
  { name: "Documentary", isSelected: false },
  { name: "Drama", isSelected: false },
  { name: "Family", isSelected: false },
  { name: "Fantasy", isSelected: false },
  { name: "Horo", isSelected: false },
];
</script>

<style></style>
