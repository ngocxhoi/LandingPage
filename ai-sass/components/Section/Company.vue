<template>
  <section class="relative text-center my-9">
    <p class="text-[16px] font-bold text-washed-purple-900">
      HELPING PEOPLE CONNECT WITH AI AT{" "}
    </p>
    <ul
      class="overflow-hidden flex after:content[''] after:from-brand-dark after:to-transparent after:bg-gradient-to-l after:right-0 after:top-0 after:bottom-0 after:w-20 after:z-10 after:absolute before:content[''] before:from-brand-dark before:to-transparent before:bg-gradient-to-r before:left-0 before:top-0 before:bottom-0 before:w-20 before:z-10 before:absolute"
    >
      <li
        v-for="e in 2"
        :key="e"
        class="flex flex-nowrap animate-[slide_20s_linear_infinite]"
      >
        <div
          v-for="company in companies"
          :key="company.name"
          class="relative w-[150px] m-20 my-10 shrink-0 flex items-center"
        >
          <NuxtImg
            :src="company.logo"
            alt=""
            width="150"
            class="object-contain max-w-none"
          />
        </div>
      </li>
    </ul>
  </section>
</template>

<script lang="ts" setup>
const companies = [
  { name: "Company1", logo: "/images/company1.png" },
  { name: "Company2", logo: "/images/company2.png" },
  { name: "Company3", logo: "/images/company3.png" },
  { name: "Company4", logo: "/images/company4.png" },
];
</script>
