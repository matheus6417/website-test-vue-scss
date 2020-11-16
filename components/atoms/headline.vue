<template>
  <header class="container"
  >
    <h3
      class="lined-headline"
    >
        {{data.text}}
    </h3>
  </header>
</template>
<script>
export default {
  props: ["data"],
}
</script>
<style scoped lang="scss">
@import '../../assets/css/base/fonts';
.lined-headline {
  color: $grey-1;
  font-family: $font-family-base;
  font-weight: 500;
  display: table;
  white-space: wrap;
  
}
@media screen and(min-width:  $screen-md) {
.lined-headline {
  white-space: nowrap;
  &:before {
    right: 1.5%;
  }
  &:after {
    left: 1.5%;
  }
  &:before, &:after {
    border-top: 1px solid #00000021;
    content: '';
    display: table-cell;
    position: relative;
    transform: translateY(50%);
    width: 50%;
  }
}
}
</style>
