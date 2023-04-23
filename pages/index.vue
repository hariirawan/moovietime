<template>
  <div class="py-[51px]">
    <swiper
      :slides-per-view="2.5"
      @slideChange="onSlideChange"
      :space-between="24"
      :centered-slides="true"
      :loop="true"
      :autoplay="{
        delay: 7000,
      }"
      :pagination="paginationOptions"
      :modules="modules"
    >
      <swiper-slide v-for="(item, index) in data" :key="index">
        <slide
          :name="item.name"
          :image="item.image"
          :rating="item.rating"
          :year="item.year"
        />
      </swiper-slide>
    </swiper>
  </div>

  <discover />
</template>

<script lang="ts" setup>
import {  Pagination, Swiper as SwiperType } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import 'swiper/css';
import 'swiper/css/pagination';

const { data } = useListMovies();
const indexSlide = ref(0);

const paginationOptions = {
  clickable: true,
};

const modules = [Pagination]

const onSlideChange = (swiper: SwiperType) => {
  indexSlide.value = swiper.activeIndex;
};
</script>

<style>

.swiper-pagination{
  @apply relative mt-[41px];
}

.swiper-pagination-bullet{
  @apply h-3 w-3 rounded-full space-x-4 bg-white bg-opacity-50;
}

.swiper-pagination-bullet-active{
  @apply w-[60px] bg-carmine-pink ease-in-out transition-all duration-200;
}

</style>
