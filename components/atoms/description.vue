<template>
  <p
    :class="isBold ? 'bold' : ''"
    :style="{
      fontWeight: isBold ? '800' : '400',
      fontSize: size === 'sm' ? '0.9em' : '1em',
    }"
  >
    {{ text }}
  </p>
</template>
<script>
export default {
  props:['text', 'isBold', 'size']
}
</script>
<style scoped lang="scss">
@import "../../assets/css/base/fonts";
p {
  color: $grey-2;
  font-weight: 400;
  line-height: 2em;
  margin-bottom: $fs-large;
  &.bold {
    color: $grey-1;
  }
}
</style>