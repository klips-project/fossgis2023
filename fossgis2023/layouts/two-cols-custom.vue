<!--
  Usage:
```md
---
layout: two-cols
---
# Left
This shows on the left
::right::
# Right
This shows on the right
```
-->



<script setup lang="ts">
const props = defineProps({
  class: {
    type: String,
  },
})


</script>

<template>
  <div class="slidev-layout two-columns w-full h-full grid grid-cols-2">
    <div class="col-left" :class="props.class">
      <slot/>
    </div>
    <div class="col-right" :class="props.class">
      <slot name="right" />
    </div>
    <div class="author-logo">
      <slot name="logo"/>
    </div>
    <Footer />
  </div>
</template>

<style scoped>
.col-left,.col-right {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.slidev-layout ul {
  list-style: none !important;
}
</style>