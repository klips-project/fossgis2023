<template>
  <footer>
    <div/>
    <div/>
    <div/>
    <div/>
    <div
        class="absolute bottom-0 -left-40px progress"
        :style="`width: ${Math.floor(
        100 * ($slidev.nav.currentPage / $slidev.nav.total)
        )}%;`"
    />
    <SlideCurrentNo v-if="$slidev.nav.currentPage !== 1" className="pageNumber" />
  </footer>
</template>

<style scoped>  
footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 3vh;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  color: white;
  display: flex;
}
footer > div {
    height: 100%;
}
footer > :nth-child(1) {
    background: #FAB31F;
    flex: 1;
}
footer > :nth-child(2) {
    background: #E5753A;
    flex: 1;
}
footer > :nth-child(3) {
    background: #E36122;
    flex: 1;
}
footer > :nth-child(4) {
    background: #e55f25;
    flex: 50;
}

.progress {
    mix-blend-mode: soft-light;
    height: 0.5vh;
    background: white;
    transition: width 1s;
}

.pageNumber {
    position: absolute;
    padding: 10px;
}
</style>