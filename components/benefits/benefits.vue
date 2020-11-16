<template>
  <div class="benefits container-md">
    <div class="benefits__container">
      <heading style="margin-bottom:5rem" :size="'md'" :text="data.title" />
      <div class="benefits__benefits">
        <div class="benefit" v-for="(feature, i) in data.features" :key="i">
          <icon  style="margin-bottom:2rem" :icon="feature.icon"></icon>
          <description :size="'sm'" :isBold="true" :text="feature.title" />
          <description :size="'sm'" :text="feature.description" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import description from '../atoms/description.vue';
import icon from '../atoms/icon.vue';
import heading from '../atoms/heading.vue'
export default {
  components: {
    icon,
    description,
    heading 
    },
  props: ["data"],
}
</script>
<style scoped lang="scss">
@import "../../assets/css/base/fonts";
.benefits__benefits {
  display: flex;
  flex-wrap: wrap;
  grid-template-columns: 1fr;
  grid-gap: 4rem;
  display: grid;
}

@media screen and(min-width:  $screen-md) {
  .benefits__benefits {
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 5rem;
}
}
@media screen and(min-width: $screen-sm) and (max-width: $screen-md) {
  .benefits__benefits {
  grid-template-columns: 1fr 1fr;
  grid-gap: 4rem;
}
}
</style>