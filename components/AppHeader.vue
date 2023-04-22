<template>
  <header class="w-full bg-white bg-opacity-5 font-montserrat relative z-50">
    <div
      class="mx-auto max-w-7xl flex flex-row items-center h-16 space-x-[48px]"
    >
      <nuxt-link to="/">
        <img
          src="/icons/MoovieTime-Logo.png"
          class="h-[31px] overflow-hidden"
        />
      </nuxt-link>
      <autocomplate />
      <ul class="flex flex-row space-x-[48px] text-white">
        <li class="relative flex flex-row items-center">
          <Menu>
            <div class="relative w-full">
              <MenuButton
                class="font-montserrat outline-none flex"
                @mouseenter="({ target }) => target.click()"
              >
                <img
                  src="/icons/iconfinder_view-grid.png"
                  class="h-[20px] mr-[11px] relative"
                />
                CATEGORIES
              </MenuButton>
              <transition
                enter-active-class="transition duration-100 ease-out"
                enter-from-class="transform scale-95 opacity-0"
                enter-to-class="transform scale-100 opacity-100"
                leave-active-class="transition duration-75 ease-in"
                leave-from-class="transform scale-100 opacity-100"
                leave-to-class="transform scale-95 opacity-0"
              >
                <MenuItems
                  class="absolute bg-white w-full text-dark z-50 rounded-md py-4 px-4 space-y-2 outline-none"
                >
                  <NuxtLink to="/movies" >
                    <div
                      v-for="(item, idx) in genres"
                      :key="idx"
                      class="cursor-pointer"
                    >
                      {{ item.name }}
                    </div>
                  </NuxtLink>
                </MenuItems>
              </transition>
            </div>
          </Menu>
        </li>
        <li>
          <nuxt-link to="/movies"> MOVIES </nuxt-link>
        </li>
        <li>TV SHOWS</li>
        <li>LOGIN</li>
      </ul>
    </div>
  </header>
</template>

<script lang="ts" setup>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";

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
