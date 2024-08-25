<template>
  <div class="w-full min-h-[500px] mt-4 border-t border-neutrals-11">
    <div
      class="w-full max-w-full lg:max-w-[90%] px-[30px] lg:px-[103px] pt-[100px] mx-auto"
    >
      <div class="w-full">
        <NuxtLink href="/" class="w-auto shrink-0 flex justify-start">
          <NuxtImg
            src="/images/logo.png"
            alt="Revd.ai Logo"
            width="126"
            height="34"
          />
        </NuxtLink>
        <p class="mt-4 text-[15.05px] text-white/90 font-normal">
          Lorem ipsum dolor sit amet consectetur. Viverra accumsan nunc elit eu
          morbi eros quisque. Vitae feugiat ipsum lectus amet suspendisse nullam
          feugiat purus leo. Tellus tellus hac orci vitae.
        </p>
      </div>
      <div class="w-full flex flex-wrap items-start pt-10">
        <ul
          v-for="(menu, index) in FOOTER_MENUS"
          :key="index"
          class="flex-1 basis-1/3 lg:basis-0"
        >
          <li class="mb-2">
            <h5 class="text-[18.81px] font-semibold text-white">
              {{ menu.title }}
            </h5>
          </li>
          <li v-for="item in menu.items" :key="item.id" class="mb-2">
            <NuxtLink href="#" class="text-[15px] text-white/90 font-normal">
              {{ item.title }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { FOOTER_MENUS } from "~/access/data/index";
</script>
