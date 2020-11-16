<template>
  <div :class="iconStyle ? iconStyle : 'icon-filled-square'">
    <asset
      :imageURL="`icons/${this.icon}`"
      :alt="`icons/${this.icon}`"
    />
  </div>
</template>

<script>
export default {
  props: ["icon", "iconStyle"],
};
</script>
<style scoped lang="scss">
.icon-filled-square {
  background: #f1ecf4;
  height: 54px;
  width: 54px;
  min-width: 54px;
  display: flex;
  justify-content: center;
  & > * {
    margin: auto;
  }
}
.icon {
  height: 36px;
  width: 36px;
  min-width: 36px;
  display: flex;
  justify-content: center;
  & > * {
    margin: auto;
  }
}
</style>