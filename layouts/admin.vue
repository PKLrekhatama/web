<template>
  <div>
    <div class="parent ">
      <div class="div1">
        <sidebarAdmin />
      </div>
      <div class="div2 sticky top-0 left-0">
        <navbarAdmin />
      </div>
      <div class="div3">
        <slot />
      </div>
    </div>
  </div>
</template>

<style scoped>
.parent {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: 0.5fr repeat(5, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
}

.div1 {
  grid-area: 1 / 1 / 7 / 2;
}
.div2 {
  grid-area: 1 / 2 / 2 / 6;
}
.div3 {
  grid-area: 2 / 2 / 7 / 6;
}
</style>
