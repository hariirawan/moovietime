<template>
  <div class="py-[51px]">
    <swiper
      :slides-per-view="3"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
      class="space-x-6"
      :modules="[Controller]"
      :controller="{ control: firstSwiper }"

    >
      <swiper-slide v-for="(item, index) in data.slice(0,4)" :key="index">
        <slide :name="item.name" :image="item.image" :rating="item.rating" :year="item.year"/>
      </swiper-slide>
    </swiper>

  </div>
  <div class="flex flex-row justify-center space-x-4 pb-[41px]">
    <div v-for="(item, index) in  data.slice(0,4)" :key="index" :class="indexSlide == index? 'w-[60px] h-3 rounded-full bg-carmine-pink space-x-4 ease-in-out transition-all duration-200':' h-3 w-3 rounded-full space-x-4 bg-white bg-opacity-50'"/>
  </div>
  <discover />
</template>

<script lang="ts" setup>
import {Controller, Swiper as SwiperType} from 'swiper';
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const {data} = useListMovies();
const firstSwiper = ref(null);
const indexSlide = ref(0);

const onSwiper = (swiper:SwiperType) => {
  console.log(swiper.activeIndex);
};
const onSlideChange = (swiper:SwiperType) => {
  indexSlide.value = swiper.activeIndex
};
</script>
