<template>
  <div class="nav-wrapper">
    <div class="content">
      <slot />
    </div>
    <Nav />
  </div>
</template>

<script lang="ts">
export default {
  name: "Layout",
};
</script>

<style lang="scss" scoped>
.nav-wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.content {
  overflow: auto;
  flex-grow: 1;
  overflow: auto;
}
</style>
