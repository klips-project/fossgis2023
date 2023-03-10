
<script>
import Footer from './footer_klips.vue'

export default {
  components: {
    Footer
  }
}
</script>
<!-- default.vue -->
<template>
  <div class="slidev-layout default cover center">
    <img src="/fossgis.png" class="start-logo" />
    <slot />
  <Footer />
  </div>
</template>

<style>
.cover {
    background-image: url("/header_upper_left.svg");
    background-repeat: no-repeat;
    margin: auto;
}
.start-logo {
  position: absolute;
  top: 0;
  right: 0;
  width: 125px;
  padding: 10px;
}
</style>
