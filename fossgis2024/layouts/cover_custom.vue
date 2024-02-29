<script setup lang="ts">
import { computed } from "vue";
const props = defineProps({
  class: {
    type: String,
  },
});
</script>
<template>
  <div class="slidev-layout cover text-center flex">
    <div class="my-auto w-full">
      <slot />
      <div class="logos" :class="props.class">
        <slot name="logos" />
      </div>
      <div class="authors py-4" :class="props.class">
        <slot name="authors" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.logos {
  font-family: 'Lato' !important;
  display: flex;
  align-items: center !important;
  height: 150px;
  justify-content: center;
  padding-top: 10vh;
}
</style>