<template>
  <div class="py-[56px]">
    <swiper
      :slides-per-view="3"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
      class="space-x-6"

    >
      <swiper-slide v-for="(item, index) in list" :key="index">
        <slide/>
      </swiper-slide>
    </swiper>
  </div>
  <discover />
</template>

<script lang="ts" setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const list = new Array(9);

const onSwiper = (swiper: any) => {
  console.log(swiper);
};
const onSlideChange = () => {
  console.log("slide change");
};
</script>
