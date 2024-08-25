<template>
  <section
    class="w-full px-4 sm:px-6 mt-[200px] flex justify-center items-center flex-col relative"
  >
    <div class="flex justify-center items-center max-w-[60%] lg:max-w-[100%]">
      <SectionTitle
        pill="Pricing Plan"
        title="Unlimited pricing plans"
        :isCurveline="false"
      />
    </div>

    <div
      class="w-full max-w-xs flex flex-col-reverse lg:flex-row gap-4 justify-center sm:items-stretch mt-14 mx-auto"
    >
      <SectionPricingCard
        v-for="plan in PRICING_CARDS"
        :key="plan.planType"
        class="border rounded-2xl background-blur-3xl relative border-[#282829]"
        :class="{
          'border-brand-primary-purple': plan.planType == PRICING_PLAN.PREMIUM,
        }"
      >
        <template #cardHeader>
          <div class="w-full">
            <template v-if="plan.planType === PRICING_PLAN.PREMIUM">
              <div
                class="w-[100%] blur-[120px] rounded-full h-56 bg-brand-primary-purple/80 -z-10 top-4 absolute"
              />

              <span class="absolute top-4 right-6">
                <SvgGlassSquare />
              </span>
            </template>
            <h1 class="text-3xl font-semibold text-neutrals-4">
              {{ plan.typeName }}
            </h1>
          </div>
        </template>

        <template #cardBody>
          <div class="p-0">
            <div class="flex items-center">
              <span class="text-sm text-neutrals-6">$</span>
              <h5 class="text-[28px] text-neutrals-6">
                {{ plan.price }}
                <span class="!text-[16px] text-neutrals-8">
                  {{
                    plan.duration === DURATION.MONTHLY
                      ? "/mo"
                      : plan.duration === DURATION.YEARLY
                      ? "/yr"
                      : ""
                  }}
                </span>
              </h5>
            </div>
            <p class="text-washed-purple-800">{{ plan.description }}</p>
            <button
              class="whitespace-nowrap w-full h-[42px] mt-4 p-[1px] bg-gradient-to-r from-[#201F30] to-[#666666]/30 rounded-[15px]"
            >
              <span
                class="flex items-center gap-3 justify-center w-full h-full rounded-[15px] bg-gradient-to-tr from-black to-[#46445b]/5 text-[17px] font-normal text-[#8D8C95]"
              >
                {{
                  plan.planType === PRICING_PLAN.ENTERPRISE
                    ? "Contact Us"
                    : "Get Started"
                }}
              </span>
            </button>
          </div>
        </template>

        <template #cardFooter>
          <p class="font-normal text-[14px] text-white mb-4">
            {{ plan.highlightFeature }}
          </p>
          <ul class="font-normal flex mb-2 flex-col gap-3">
            <li
              v-for="(feature, index) in plan.features"
              :key="index"
              class="flex items-center text-neutrals-6 text-[15px]"
            >
              <SvgGlassSend />
              <span>{{ feature }}</span>
            </li>
          </ul>
        </template>
      </SectionPricingCard>
    </div>
  </section>
</template>

<script lang="ts" setup>
enum PRICING_PLAN {
  BASIC = "Basic Plan",
  PREMIUM = "Premium Plan",
  ENTERPRISE = "Enterprise Plan",
}

enum DURATION {
  MONTHLY = "MONTHLY",
  YEARLY = "YEARLY",
}

const PRICING_CARDS = [
  {
    planType: PRICING_PLAN.BASIC,
    typeName: "Basic",
    duration: "",
    price: "0",
    description: "Limited block trials for teams",
    highlightFeature: "",
    features: [
      "Unlimited blocks for teams",
      "Limited file uploads",
      "30 day page history",
    ],
  },
  {
    planType: PRICING_PLAN.PREMIUM,
    duration: DURATION.MONTHLY,
    typeName: "Premium",
    price: "29.99",
    description: "Billed annually. $14.5 billed monthly",
    highlightFeature: "Everything in free +",
    features: [
      "Unlimited blocks for teams",
      "Unlimited file uploads",
      "30 days page history",
    ],
  },
  {
    planType: PRICING_PLAN.ENTERPRISE,
    duration: DURATION.YEARLY,
    typeName: "Enterprise",
    price: "299.9",
    description: "Billed annually.",
    highlightFeature: "Everything in free +",
    features: [
      "Unlimited blocks for teams",
      "Unlimited file uploads",
      "100 days page history",
    ],
  },
];
</script>
