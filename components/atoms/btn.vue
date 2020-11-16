<template>
  <a href="#" class="button">{{
    btnText
  }}</a>
</template>

<script>
export default {
  props:['btnText']
}
</script>

<style scoped lang="scss">
@import "../../assets/css/base/fonts";

.button {
  align-items: center;
  background-color: #f0783c;
  border-radius: 2px;
  border: none;
  color: #fff;
  cursor: pointer;
  text-align:center;
  display: inline;
  font-size: $fs-base * 0.8;
  font-weight: 700;
  justify-content: center;
  line-height: 1.2;
  width: 194px;
  padding: 2rem;
  -webkit-transition: all 0.2s;
  -moz-transition: all 0.2s;
  -ms-transition: all 0.2s;
  -o-transition: all 0.2s;
  transition: all 0.2s;
}
.button:hover {
  background-color: #ffa161;
}
</style>