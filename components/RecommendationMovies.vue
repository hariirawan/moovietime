<template>
  <div>
    <h3 class="font-montserrat text-sm font-semibold pb-9 text-white">RECOMMENDATAION MOVIES</h3>
    <div class="grid grid-cols-5 gap-[21px] ">
        <div v-for="(item, index) in data.slice(0,5)" :key="index">
          <card-movie :id="index" :name="item.name" :year="item.year" :image="item.image" :rating="item.rating"/>
        </div>
      </div>
  </div>
</template>


<script lang="ts" setup>
const {data} = useListMovies();
</script>
