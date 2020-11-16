<template>
  <div class="component-accordion">
    <div class="accordion-item" v-for="(faq, i) in faqs" :key="i">
      <div class="accordion-item-header" @click="itemOpened === i ?  itemOpened = null : itemOpened = i">
        <description :size="'sm'" :isBold="true" :text="faq.question" />
        <icon
          :icon-style="'icon'"
          :icon="itemOpened === i ? 'close.svg' : 'open.svg'"
        ></icon>
      </div>
      <div
        style="display: flex; overflow: hidden"
        class="accordion-item-content"
        :class="itemOpened === i ? 'open' : ''"
      >
        <description :size="'sm'" :text="faq.answer" />
      </div>
    </div>
  </div>
</template>

<script>
import icon from '../atoms/icon.vue';
import description from '../atoms/description.vue';
export default {
  components: {
    description,
    icon,
  },
  data(){
    return {
      itemOpened: 0
    }
  },
  props: ["faqs"],
};
</script>
<style scoped lang="scss">
@import "../../assets/css/base/fonts";
@import "../../assets/css/utilities/variables";
.accordion-header-icon-wrapper {
  position: relative;
  display: flex;
  width: 16px;
  height: 16px;
  justify-content: center;
  align-items: center;
}
.accordion-item-header {
  position: relative;
  z-index: 1000;
  display: flex;
  padding-left: 0;
  justify-content: space-between;
  align-items: center;
  color: $grey-1;
  cursor: pointer;
}
.accordion-item {
  border-bottom: 1px solid #dbdbdb;
  padding: 24px 0;
  &:first-child {
    padding-top: 0;
  }
}
.component-accordion {
  width: 100%;
  min-height: 100px;
}
.accordion-column {
  padding: 10px 0;
}
.accordion-item-content {
  display: flex;
  overflow: hidden;
  padding: 0 2rem 0 0;
  opacity: 0;
  transition: all 0.1s;
  height: 0;
  justify-content: flex-start;
  align-items: center;
  &.open {
    opacity: 1;
    padding: 2rem 2rem 0 0;
    transition: all 0.2s;
    height: auto;
  }
}

@media (max-width: $screen-xs) {
  .accordion-item-header {
    padding-top: 10px;
    padding-bottom: 10px;
  }
  .accordion-column {
    padding-top: 0;
  }
}
</style>