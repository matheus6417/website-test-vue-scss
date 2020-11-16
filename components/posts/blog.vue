<template>
  <div class="blog">
    <div class="container blog__container">
      <div class="blog__categories">
        <h3
          v-for="(filter, i) in data.filters"
          :key="filter"
          class="blog__category"
          :class="filteredByCategory === filter ? 'active' : ''"
          @click="filteredByCategory = filter"
        >
          {{ filter }}
        </h3>
      </div>
      <div class="blog__cards posts_list container-md">
        <a
          v-for="(item, i) in blogitems.filter((item) =>
            filteredByCategory !== 'All'
              ? item.category === filteredByCategory.toLowerCase()
              : item
          )"
          :key="i"
          href="#"
          class="post"
          :class="`posts--${item.category}`"
          ><div class="post__image cover_image">
            <asset :imageURL="item.image" :alt="item.image" />
          </div>
          <div class="post__text">
            <span class="post__category">{{ item.category }}</span>
            <heading class="post__heading" :size="'sm'" :text="item.title" />
            <span class="posts__metas"
              ><span class="post__meta">{{ item.date }}</span
              ><span class="post__meta">{{ item.author }}</span></span
            >
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import heading from '../atoms/heading.vue';
export default {
  components: {
    heading,
  },
  props: ["data"],
  data(){
    return {
      filteredByCategory: 'All',
      blogitems:[
        {
          image:'blog/image-02.jpg', 
          category: 'insights',
          title:'Aliquam convallis iaculis et sodales non justo.', 
          date:'Jan 01, 2020', 
          author:"Robert O'Malley", 
        },
        {
          image:'blog/image-03.jpg', 
          category: 'news',
          title:'Orem ipsum dolor sit amet consectetur adipiscing', 
          date:'Jan 13, 2020', 
          author:"Robert O'Malley", 
        },
         {
          image:'blog/image-04.jpg', 
          category: 'events',
          title:'Sed eurs-us. bibendum feugíat. In orcí sapien', 
          date:'Jan 11, 2020', 
          author:"Robert O'Malley", 
        }
      ]
    }
  }
}
</script>
<style scoped lang="scss">
@import "../../assets/css/base/fonts";
@import "../../assets/css/utilities/variables";
::-webkit-scrollbar {
  display: none;
}
.post {
  margin-bottom: 4rem;
  display: flex;
  flex-direction: column;
  &:hover .post__heading {
    text-decoration: underline;
  }
}
.post__image {
  border-radius: 2px;
  height: 203px;
  margin-bottom: 20px;
  position: relative;
  width: 100%;
}
.post__category {
  color: $gull_gray;
  display: block;
  font-size: $fs-base * 0.8;
  font-weight: 500;
  margin-bottom: 4px;
  text-transform: uppercase;
  transition: all 0.2s;
}
.post__heading {
  transition: all 0.2s;
}
.post__text {
  flex-grow: 1;
}
.posts__metas {
  color: $grey-2;
  display: block;
  margin-top: auto;
}
.post__meta {
  display: inline-block;
  font-size: $fs-base * 0.8;
  font-weight: 500;
  opacity: 0.7;
  + .post__meta:before {
    background-color: $grey-2;
    content: "";
    display: inline-block;
    height: 2px;
    margin: 0 4px;
    position: relative;
    top: -4px;
    width: 12px;
  }
}
.posts--events {
  .post__category {
    color: $grey-1;
  }
  .post__image:before {
    color: $grey-1;
    color: $grey-1;
  }
}
.posts--insights {
  .post__category {
    color: $tertiary;
  }
  .post__image:before {
    color: $tertiary;
  }
}

.blog__category {
  cursor: pointer;
  color: $grey-2;
  font-size: $fs-h5;
  font-weight: 400;
  padding: 0 2rem;
  &.active {
    color: $grey-1;
    text-decoration: underline;
  }
  &:hover:not(.current) {
    color: $color_dove_gray_approx;
  }
}

.posts--news .post__category {
  color: $primary;
}
.posts--events .post__category {
  color: $blue;
}

.cover_image {
  height: 100%;
  overflow: hidden;
  position: relative;
  width: 100%;
  img {
    display: block;
    height: 100%;
    object-fit: cover;
    transition: all 0.2s;
    width: 100%;
  }
}
.posts_list {
  display: flex;
  flex-wrap: wrap;
}
.blog__container {
  display: flex;
  flex-direction: column;
}
.blog__categories {
  display: flex;
  justify-content: flex-start;
  margin-bottom: 38px;
  overflow: auto;
}

.blog__cards {
  margin-bottom: 10px;
}
@media screen and(min-width:  $screen-md) {
  .blog__category {
    font-size: $fs-h3;
    padding: 0 3rem;
  }

  .posts_list {
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 5rem;
    display: grid;
  }
  .blog__categories {
    display: flex;
    justify-content: center;
  }
}
@media screen and(min-width: $screen-sm) and (max-width: $screen-md) {
  .blog__categories {
    overflow: auto;
  }
  .posts_list {
    grid-template-columns: 1fr 1fr;
    grid-gap: 3rem;
    display: grid;
  }
}
</style>