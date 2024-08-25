<template>
  <div>
    <section class="flex flex-col gap-4 justify-center items-center">
      <div
        v-if="Boolean(pill)"
        class="rounded-full p-[1px] font-normal text-[11.87px] bg-gradient-to-r from-brand-primary-blue to-brand-primary-purple mb-5"
      >
        <div class="rounded-full mx-auto px-4 py-2 bg-black">
          {{ pill }}
        </div>
      </div>

      <template v-if="Boolean(subheading)">
        <div class="relative">
          <h2
            class="text-center text-[35px] sm:text-[55px] sm:max-w-[750] md:text-center leading-tight font-bold"
          >
            {{ title }}
          </h2>
          <span v-if="isCurveline" class="absolute bottom-0 right-11">
            <SvgCurveline />
          </span>
        </div>
        <p
          class="text-washed-purple-700 sm:max-w-[500px] text-center text-[16px] sm:text-[18px]"
        >
          {{ subheading }}
        </p>
      </template>
      <div v-else class="relative">
        <h1
          class="text-center text-[45px] sm:text-[65px] sm:max-w-[850px] md:text-center leading-tight font-bold"
        >
          {{ title }}
        </h1>
        <span
          v-if="isCurveline"
          class="absolute -bottom-2 right-16 lg:right-24"
        >
          <SvgCurveline />
        </span>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  title: string;
  subheading?: string;
  pill?: string;
  isCurveline?: boolean;
}>();

const { title, pill, subheading, isCurveline } = toRefs(props);
</script>

<style></style>
