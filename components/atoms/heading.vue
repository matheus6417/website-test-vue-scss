<template>
  <h2 class="heading" :class="size">{{ text }}</h2>
</template>

<script>
export default {
  props:['text', 'size']
}
</script>

<style scoped lang="scss">
@import "../../assets/css/base/fonts";
.heading {
  max-width: 46ch;
}
.sm {
  margin-bottom: 0;
  font-weight: 600;
  line-height: $fs-h4 * 1.3;
  font-size: $fs-h4;
}
.md {
  margin-bottom: 1.5rem;
  font-weight: 600;
  font-size: $fs-medium;
}
.lg {
  margin-bottom: 0;
  font-weight: 800;
  font-size: $fs-large;
  line-height: $fs-large * 1.2;
}
</style>