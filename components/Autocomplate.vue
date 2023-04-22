<template>
  <div class="relative w-full bg-black bg-opacity-25 flex-1 z-50 rounded-md">
    <Combobox v-model="selectedPerson">
      <div class="relative flex items-center w-full py-2 px-3">
        <img src="/icons/iconfinder_movie.png" class="h-[24px] mr-[15px]" />
        <ComboboxInput
          @change="query = $event.target.value"
          class="w-full h-full bg-black bg-opacity-0 outline-none text-white"
          placeholder="Find Movie"
        />
        <!-- <input class="w-full h-full bg-black bg-opacity-0 outline-none text-white" placeholder="Find movie" v-model="query"/> -->
        <img src="/icons/iconfinder_search.png" class="h-[16px]" />
      </div>
      <ComboboxOptions class="absolute w-full">
        <NuxtLink to="/movie/1">

          <ComboboxOption
          v-for="(person, index) in filteredPeople"
          :key="index"
          :value="person"
          class="bg-black bg-opacity-90 px-3 text-white py-[9px]"
          >
          {{ person }}
        </ComboboxOption>
      </NuxtLink>
      </ComboboxOptions>
    </Combobox>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from "vue";
import {
  Combobox,
  ComboboxInput,
  ComboboxOptions,
  ComboboxOption,
} from "@headlessui/vue";

const people = [
  "Durward Reynolds",
  "Kenton Towne",
  "Therese Wunsch",
  "Benedict Kessler",
  "Katelyn Rohan",
];
const selectedPerson = ref("");
const query = ref("");

const filteredPeople = computed(() =>
  query.value === ""
    ? people
    : people.filter((person) => {
        return person.toLowerCase().includes(query.value.toLowerCase());
      })
);
</script>
