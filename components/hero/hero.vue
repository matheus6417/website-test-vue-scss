<template>
  <div class="hero__panel container-md">
    <div class="hero__content">
      <heading :size="'lg'" :text="data.title" />
      <description style="margin-bottom: 2rem" :text="data.description" />
      <btn :btn-text="data.btnText" />
    </div>
    <div class="hero__image_wrapper">
      <asset :imageURL="data.imgUrl" :alt="data.imgUrl" />
    </div>
  </div>
</template>
<script>
import description from '../atoms/description.vue';
import heading from '../atoms/heading.vue';
import btn from '../atoms/btn.vue'
export default {
  components: {
    heading,
		description, 
		btn },
  props: ["data"]
}
</script>
<style scoped lang="scss">
.hero__panel {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  grid-template-columns: 1fr;
  grid-gap: 2rem;
  display: grid;
}
.hero__content {
  display: flex;
  flex-direction: column;
  vertical-align: middle;
  margin: auto;
}
.hero__image_wrapper {
  grid-column: 1;
  grid-row: 1;
  width: 100%;
  margin-right: 0;
  margin-left: 0;
}
@media screen and(min-width:  $screen-md) {
  .hero__panel {
    grid-template-columns: 1fr 1fr;
  }
  .hero__image_wrapper {
    grid-column: 2;
    grid-row: 1;
    width: 504px;
    margin-right: 0;
    margin-left: auto;
  }
}
</style>