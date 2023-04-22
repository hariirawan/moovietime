<template>
  <div>
    <img src="/images/bg-detail.png" class="absolute top-0 left-0 right-0 z-0" />
    <div class="relative">
      <div class="relative max-w-7xl mx-auto mt-[186px] flex mb-[30px]">
        <img src="/images/wonder-woman.png" class="absolute w-[220px] z-50" />
        <div class="pl-[255px] pt-[17px] text-white">
          <span class="text-sm font-medium">2020</span>
          <h3 class="font-bold text-4xl">Wonder Woman 1984</h3>
          <span class="text-sm font-medium">Fantasy, Action, Adventure</span>
        </div>
      </div>
      <div class="relative w-full bg-black bg-opacity-50 text-white">
        <div class="max-w-7xl mx-auto h-[80px] flex items-center pl-[255px]">
          <img src="/icons/Star.png" class="mr-6" />
          <span class="text-4xl font-semibold mr-3">7.0</span>
          <div class="flex flex-1 divide-x space-x-12">

            <div >
              <div class="font-medium text-xs text-white text-opacity-50">
                USER SCORE
              </div>
              <div class="font-medium text-xs text-white">3621 VOTES</div>
            </div>
            <div class="pl-12">
              <div class="font-medium text-xs text-white text-opacity-50">
                STATUS
              </div>
              <div class="font-medium text-xs text-white">RELEASED</div>
            </div>
            <div class="pl-12">
              <div class="font-medium text-xs text-white text-opacity-50">
                LANGUAGE
              </div>
              <div class="font-medium text-xs text-white">ENGLISH</div>
            </div>
            <div class="pl-12">
              <div class="font-medium text-xs text-white text-opacity-50">
                BUDGET
              </div>
              <div class="font-medium text-xs text-white">$200,000,000.00</div>
            </div>
            <div class="pl-12">
              <div class="font-medium text-xs text-white text-opacity-50">
                PRODUCTION
              </div>
              <div class="font-medium text-xs text-white">DC ENTERTAINMENT</div>
            </div>
          </div>
        </div>
      </div>

      <div class="w-full h-[540px] bg-white">
        <div class="max-w-7xl mx-auto pl-[255px]">
          <h3 class="text-sm font-semibold pt-[32px] pb-[9px] text-red-500">Overview</h3>
          <p class="w-3/5">
            Wonder Woman comes into conflict with the Soviet Union during the
            Cold War in the 1980s and finds a formidable foe by the name of the
            Cheetah.
          </p>
        </div>

        <div class="max-w-7xl mx-auto">
          <h3 class="text-sm font-semibold pt-[32px] pb-[9px]  text-red-500">Reviews</h3>
          <div class="flex space-x-8">
            <Review />
            <Review />
          </div>
        </div>
      </div>
      <div class="relative w-full bg-dark py-12">
        <div class="max-w-7xl mx-auto">
          <RecommendationMovies />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
definePageMeta({
  layout: "detail",
});
</script>
