<template>
  <div class="slider container">
    <div class="slider__heading container-md">
      <heading :size="'lg'" :text="data.title" />
      <div class="slider_arrows">
        <div class="slider_arrows__arrow slider_arrows__arrow--prev">
          <icon :icon-style="'icon'" :icon="'arrow-02.svg'"></icon>
        </div>
        <div class="slider_arrows__arrow slider_arrows__arrow--next">
          <icon :icon-style="'icon'" :icon="'arrow-01.svg'"></icon>
        </div>
      </div>
    </div>
    <div class="slider__slider_section">
      <div class="slider__slider_container">
        <div class="slider__slider_wrapper">
          <div class="slider__outer">
            <div class="slider__ovh" style="height: 352px">
              <div class="slider__inner">
                <div
                  class="slider__slider slider__slider slider__carousel slider__subpixel slider__calc slider__horizontal"
                  style="
                    transition-duration: 0s;
                    transform: translate3d(0%, 0px, 0px);
                  "
                >
                  <a
                    v-for="(item, i) in slides"
                    :key="i"
                    href="#"
                    class="sector slider__item slider__slide-active"
                    ><div class="sector__image cover_image">
                      <asset
                        :imageURL="item.imgUrl"
                        :alt="item.title"
                      />
                    </div>
                    <heading
                      class="sector__heading"
                      :size="'sm'"
                      :text="item.title"
                    />
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import heading from '../atoms/heading.vue';
import icon from '../atoms/icon.vue';
export default {
  data(){
    return {
      slides:[
        { 
          title: 'Slider Item 1',
          imgUrl: 'slider/image-05.jpg'
        },
        { 
          title: 'Slider Item 2',
          imgUrl: 'slider/image-06.jpg'
        },
        { 
          title: 'Slider Item 3',
          imgUrl: 'slider/image-07.jpg'
        },
        { 
          title: 'Slider Item 4',
          imgUrl: 'slider/image-08.jpg'
        }
      ]
    }
  },
  components: {
    icon,
    heading,
  },
  props: ["data"],
}
</script>
<style scoped lang="scss">
@import "../../assets/css/utilities/variables";
@import "../../assets/css/base/fonts";
.slider__outer {
  padding: 0 !important;
}
.slider__slider {
  transition: all 0s;
}
.slider__ovh {
  overflow-x: auto;
  overflow-y: hidden;
}
::-webkit-scrollbar {
  display: none;
}
.cover_image {
  overflow: hidden;
}

.slider__heading {
  padding: 0;
  display: flex;
  justify-content: space-between;
  margin-bottom: 3rem;
}
.slider_arrows {
  display: flex;
  transition: all 0.2s;
}
.slider_arrows__arrow {
  background-color: $gull_gray;
  cursor: pointer;
  line-height: 1;
  height: 42px;
  color: $white;
  width: 47px;
  align-items: center;
  display: flex;
  justify-content: center;
  transition: all 0.2s;
  &:hover {
    color: $white;
  }
}
.slider {
  padding-top: 27px;
  .sector {
    display: block;
    &:hover .sector__heading {
      color: $tertiary;
      &:after {
        opacity: 1;
      }
    }
  }
  .sector__image {
    height: 290px;
    margin-bottom: 27px;
    width: 100%;
  }
  .sector__heading {
    transition: all 0.2s;
    &:after {
      color: $tertiary;
      font-size: 0.6em;
      font-weight: 400;
      position: relative;
      top: -0.1em;
      color: inherit;
      font-size: 0.45em;
      margin-left: 12px;
      opacity: 0;
      transition: all 0.2s;
    }
  }
}
.slider__slider_section {
  padding: 0 2rem 12rem;
  background: linear-gradient(
    to bottom,
    $white 116px,
    $background_tertiary 116px
  );
}
.slider__slider_container {
  overflow: hidden;
  padding-right: 0;
  margin-right: auto;
  margin-left: auto;
}

.slider__horizontal.slider__subpixel {
  white-space: nowrap;
  > .slider__item {
    display: inline-block;
    vertical-align: top;
    white-space: normal;
  }
}
@media screen and(min-width: $screen-sm) {
  .slider__slider_container {
    padding-left: 100px;
  }

  .slider__slider_section {
    background: linear-gradient(
      to bottom,
      $white 50px,
      $background_tertiary 50px
    );
    padding: 0 0 15rem;
  }

  .slider__heading {
    margin-bottom: 0;
    padding:inherit;
  }
}
</style>