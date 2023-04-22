<template>
  <div class="py-[56px]">
    <swiper
      :slides-per-view="3"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
      class="space-x-6"

    >
      <swiper-slide v-for="(item, index) in data" :key="index">
        <slide :name="item.name" :image="item.image" :rating="item.rating" :year="item.year"/>
      </swiper-slide>
    </swiper>
  </div>
  <discover />
</template>

<script lang="ts" setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const {data} = useListMovies();

const onSwiper = (swiper: any) => {
  console.log(swiper);
};
const onSlideChange = () => {
  console.log("slide change");
};
</script>
