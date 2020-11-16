<template>
  <div class="faq">
    <div class="container-md faq__container">
      <div class="faq__headings">
        <heading class="faq__heading" :size="'md'" :text="data.title" />
        <description :size="'sm'" :text="data.description" />
      </div>
      <div class="faq__features">
        <accordion :faqs="data.faqs"></accordion>
      </div>
    </div>
  </div>
</template>

<script>
import description from '../atoms/description.vue';
import heading from '../atoms/heading.vue';
import accordion from '../molecules/accordion.vue';
export default {
  components: {
    accordion,
    heading,
    description,
  },
  props: ["data"],
}
</script>

<style scoped lang="scss">
@import "../../assets/css/utilities/variables";
.faq {
  padding-bottom: 8rem;
  padding-top: 5rem;
}
.faq__container {
  grid-template-columns: 1fr;
  grid-gap: 5rem;
  display: grid;
}
@media screen and(min-width: $screen-sm) {
  .faq__container {
    grid-template-columns: 1fr 2fr;
    grid-gap: 2rem;
    display: grid;
  }
  .faq__features {
    padding: 0 0 0 6.6rem;
    display: flex;
    flex-wrap: wrap;
  }
}
.faq__heading {
  padding-bottom: 0;
}
</style>