<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <div class="footer-klips">
    <div class="authors">
      <span>Christian Mayer, meggsimum - Büro für Geoinformatik</span>
      <span>Hannes Blitza, terrestris</span>
    </div>
  </div> 
</template>

<style scoped>
  .footer-klips {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100vw;
    height: 7vh;
    background: #e55f25;
    padding: 5px;
  }
  .authors {
    font-family: 'Open Sans';
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    color: white;
    justify-content: center;
    height: 100%;
  }
</style>
