<template>
  <main>
    <section
      class="overflow-hidden px-4 sm:px-6 mt-10 sm:flex gap-4 md:justify-center md:items-center"
    >
      <div class="flex flex-col">
        <div class="flex flex-col">
          <SectionTitle
            pill="✨ Your AI Workspace, Perfected"
            title="Explore the possibilities of AI Tools with Revd.ai"
            :isCurveline="true"
          />
          <div
            class="flex flex-col items-center w-full max-w-[350px] gap-3 py-5 mx-auto"
          >
            <div
              class="w-full h-[46px] relative rounded-full bg-gradient-to-r p-[1px] from-[#2A2A2A] to-[#737373] mt-5"
            >
              <input
                type="text"
                placeholder="Enter your email"
                class="w-full h-full rounded-full bg-brand-dark pl-6 text-[14px] placeholder:text-washed-purple-800"
              />
              <button
                class="absolute top-1 right-2 rounded-[28px] w-[107px] h-[37px] p-[1px] bg-gradient-to-r bg-opacity-30"
              >
                <span
                  class="flex items-center justify-center w-full text-white h-full rounded-[28px] bg-gradient-to-r from-washed-purple-700 to-primary-purple-700"
                >
                  Start Free
                </span>
              </button>
            </div>
            <p class="text-[16px] text-washed-purple-600 font-medium">
              No credit card ✨ 14-days free trial
            </p>
          </div>
        </div>
        <div
          class="relative md:mt-[-45px] sm:w-full w-[750px] flex justify-center items-center mt-[-40px] sm:ml-0 ml-[-50px]"
        >
          <NuxtImg src="/images/appBanner1.png" alt="Application Banner" />
          <div
            class="bottom-0 top-[40%] bg-gradient-to-t from-black/50 left-0 right-0 absolute z-10"
          />
        </div>
      </div>
    </section>

    <SectionCompany />
    <SectionFeature />
    <Testimonials />
    <SectionPricing />
    <SectionCallToAction />
  </main>
</template>

<script setup lang="ts">
useSeoMeta({
  title: "Overview",
});
</script>

<style></style>
