<template>
  <section
    class="w-full px-4 sm:px-6 mt-[120px] flex justify-center items-center flex-col relative"
  >
    <div
      class="w-[60%] blur-[120px] rounded-full h-32 bg-brand-primary-purple/90 -z-10 top-56 absolute"
    />
    <div
      class="flex justify-center items-center text-center max-w-full md:max-w-[60%] xl:max-w-[550px]"
    >
      <SectionTitle
        pill="Features"
        title="Work swiftly like never before"
        subheading="All AI tools you need in one place"
      />
    </div>
    <div
      class="w-full max-w-full lg:max-w-[55%] min-h-[350px] sm:h-[490px] flex items-center flex-col sm:flex-row justify-center mt-10 sm:pb-[18rem] relative"
    >
      <div
        class="z-10 flex w-[302.56px] lg:w-[500px] h-auto justify-center items-center relative sm:absolute top-0 left-0 sm:ml-0 rounded-2xl border-4 border-washed-purple-300 border-opacity-10"
      >
        <NuxtImg
          src="/images/ai-chatBanner.png"
          alt="AI Chat Banner"
          class="rounded-2xl"
        />
      </div>
      <div
        class="z-10 top-[1rem] w-[302.56px] lg:w-[500px] sm:top-[7.3rem] right-0 h-auto flex justify-center items-center relative sm:absolute sm:ml-0 rounded-2xl border-4 border-washed-purple-300 border-opacity-15"
      >
        <NuxtImg
          src="/images/ai-documentBanner.png"
          alt="AI Doc Banner"
          class="rounded-2xl"
        />
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup></script>
