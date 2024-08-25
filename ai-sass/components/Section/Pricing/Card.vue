<template>
  <div
    class="flex flex-col gap-4 relative shrink-0 w-[300px] min-h-[328px] px-[30px] py-[25px] bg-[#020014]/50"
    :class="className"
  >
    <div class="card-header">
      <slot name="cardHeader" />
    </div>
    <div class="card-body">
      <slot name="cardBody" />
    </div>
    <div class="card-footer">
      <slot name="cardFooter" />
    </div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  className?: string;
}>();
const { className } = toRefs(props);
</script>
