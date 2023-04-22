<template>
  <div class="min-w-[540px] h-[364px] mx-[33px]">
    <div class="flex flex-row">
      <img :src="props.image" class="w-[243px]" />
      <div
        class="my-[20px] bg-black flex flex-col justify-center text-white p-[24px] space-y-[11px]"
      >
        <div class="space-x-[5px] flex flex-row items-center">
          <img src="/icons/Star.png" class="h-[16.21px] w-[16.21px]" />
          <span class="font-bold text-lg">{{ props.rating }}</span>
        </div>
        <h3 class="font-medium text-xl">{{ props.name }}</h3>
        <div class="flex flex-row items-center space-x-[5px]">
          <span>2021</span>
          <div class="w-[6px] h-[6px] rounded-full bg-slate-400"></div>
          <span>2021</span>
        </div>
        <p class="font-normal text-xs">
          When the crew of a space junk collector ship called The Victory
          discovers a humanoid robot named Dorothy that's known to be a weapon
          of mass destruction, they get involved in a risky business deal which
          puts their lives at stake.
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps({
  name:String,
  image:String,
  year:String,
  rating:String
});
</script>
