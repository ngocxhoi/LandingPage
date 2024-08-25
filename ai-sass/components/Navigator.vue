<template>
  <nav
    class="sticky top-0 z-[9999] bg-brand-dark w-full px-[43px] py-[12px] h-[79px] flex justify-between items-center border-b border-neutrals-11"
  >
    <NuxtLink href="/" class="w-auto shrink-0 flex justify-start">
      <NuxtImg
        src="/images/logo.png"
        alt="Revd.ai Logo"
        width="126"
        height="34"
      />
    </NuxtLink>

    <div class="hidden lg:block">
      <ul
        class="flex items-center gap-6 px-8 py-3.5 rounded-[30px] border border-neutrals-12"
      >
        <li
          v-for="menu in menus"
          :key="menu.href"
          class="w-auto text-white text-[16px] font-normal"
        >
          <NuxtLink :href="menu.href" class="w-auto flex items-center gap-2">
            <span>{{ menu.title }}</span>
            <template v-if="menu.hasChild">
              <SvgDropDown />
            </template>
          </NuxtLink>
        </li>
      </ul>
    </div>
    <aside class="flex items-center gap-6">
      <button class="flex items-center h-10 text-[16px] font-normal text-white">
        Login
      </button>
      <button
        class="flex items-center h-10 text-[16px] whitespace-nowrap p-[1px] bg-gradient-to-r from-brand-primary-blue to-brand-primary-purple/50 rounded-[15px]"
      >
        <span
          class="flex items-center px-[23px] h-full rounded-[15px] text-[16px] bg-black font-normal text-white bg-gradient-to-tr from-black to-[#46445b]/20"
        >
          Sign up
        </span>
      </button>
    </aside>
  </nav>
</template>

<script lang="ts" setup>
const menus = [
  {
    title: "Products",
    href: "#products",
    hasChild: true,
  },
  {
    title: "Resources",
    href: "#resources",
    hasChild: true,
  },
  {
    title: "Pricing",
    href: "#pricing",
    hasChild: false,
  },
  {
    title: "Downloads",
    href: "#downloads",
    hasChild: false,
  },
  {
    title: "Contact Us",
    href: "#contact-us",
    hasChild: false,
  },
];
</script>
