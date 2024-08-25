<template>
  <div
    class="flex flex-col relative shrink-0 w-[507px] h-[244px] p-[25px] rounded-2xl bg-gradient-to-t from-[#030014] to-[#161427] from-[0%] to-[100%]"
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
