<template>
  <section
    class="w-full px-4 sm:px-6 mt-[200px] flex justify-center items-center flex-col relative"
  >
    <div
      class="w-[60%] blur-[120px] rounded-full h-32 bg-brand-primary-purple/90 -z-10 top-10 absolute"
    />

    <div class="flex justify-center items-center max-w-[60%] lg:max-w-[100%]">
      <SectionTitle
        pill="Testimonials"
        title="Trusted by all"
        subheading="Join thousands of satisfied users who rely on our platform for their
personal and professional productivity needs."
      />
    </div>
    <div
      class="w-full mt-10 px-4 sm:px-6 flex flex-col overflow-x-hidden overflow-visible"
    >
      <div
        v-for="e in 2"
        :key="randomUUID()"
        class="mt-10 flex flex-nowrap gap-6 self-start animate-[slide_250s_linear_infinite]"
        :class="{
          'flex-row-reverse animate-[slide_250s_linear_infinite_reverse] ml-[100vw]':
            e == 1,
        }"
      >
        <TestimonialCard v-for="(user, i) in DUMMY_USERS" :key="user.name">
          <template #cardHeader>
            <div class="flex items-center gap-4">
              <div
                class="avatar w-16 h-16 rounded-full p-[1px] border-1 bg-washed-purple-500"
              >
                <NuxtImg
                  :src="`https://i.pravatar.cc/180?img=${i + 9}`"
                  :alt="user.name"
                  width="64"
                  height="64"
                  class="rounded-full object-cover"
                />
              </div>
              <div>
                <h5 class="text-washed-purple-50 text-[16px] leading-[15px]">
                  {{ user.name }}
                </h5>
                <p class="text-neutrals-7 italic">
                  {{ user.name?.toLowerCase() }}
                </p>
              </div>
            </div>
          </template>

          <template #cardBody>
            <p class="text-neutrals-5 text-[18px] leading-[22px]">
              {{ user.message }}
            </p>
          </template>
        </TestimonialCard>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
import { uuidv4 as randomUUID } from "~/access/js/randomUUID";
import { DUMMY_USERS } from "~/access/data/index";
</script>
