<template>
  <div>
    <headline
      style="margin-top: 6rem; margin-bottom: 12rem"
      :data="{
        text: 'Section #1 Basic — Font Family: “Poppins”',
      }"
    />
    <hero
      style="margin-bottom: 18rem"
      :data="{
        title: 'Dignissim neque aliquet roin sed turpis et purus',
        description:
          'Proin eget sociales augue, ici finibus tortor. Etiam hendrerit sapien magna, ac pellentesque ante consectetur sit amet. Duis tempor diam erat, eu rhoncus justo oommodo neo.',
        btnText: 'FIND OUT MORE',
        imgUrl: 'hero/image-01.jpg',
      }"
    />
    <benefits
      style="margin-bottom: 20rem"
      :data="{
        title:
          'Aliquam tincidunt augue vel condimentum gravida uspe et ligula justo am maximus suscipit dui.',
        features: [
          {
            icon: 'icon-01.svg',
            title: 'High-quality, cost-effective courses',
            description:
              'Mauris at velit mattis risus gravida finielitbus condimentum quis arcu. Etiam eget erat feugiat, auctor nisi ac, semper nibh.',
          },
          {
            icon: 'icon-02.svg',
            title: 'Highly Experienced, Qualified Lecturers',
            description:
              'Deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.',
          },
          {
            icon: 'icon-03.svg',
            title: 'Easy-to-use online student portal',
            description:
              'Lorem ipsum dolor sit amet, consectetur adipiscig elit. Proin tincidunt imperdiet finibus luctus quis ligula et mauris.',
          },
        ],
      }"
    />
    <headline
      :data="{
        text: 'Section #2 Advanced — Font Family: “Poppins”',
      }"
    />
    <testimonials
      style="height: 62rem"
      :data="{
        testimonials: [
          {
            text:
              'I had an amazing time at lorem ipsum dolar consectetur adipiscing elit. Nam a dui in magna placerat finibus vitae ac nibh. I had an amazing time at lorem ipsum dolar roin',
          },
          {
            text:
              'You had an amazing time at lorem ipsum dolar consectetur adipiscing elit. Nam a dui in magna placerat finibus vitae ac nibh. I had an amazing time at lorem ipsum dolar roin',
          },
          {
            text:
              'He had an amazing time at lorem ipsum dolar consectetur adipiscing elit. Nam a dui in magna placerat finibus vitae ac nibh. I had an amazing time at lorem ipsum dolar roin',
          },
          {
            text:
              'She had an amazing time at lorem ipsum dolar consectetur adipiscing elit. Nam a dui in magna placerat finibus vitae ac nibh. I had an amazing time at lorem ipsum dolar roin',
          },
        ],
      }"
    />
    <blog
      style="margin-bottom: 16rem"
      :data="{
        filters: ['All', 'News', 'Insights', 'Events', 'Resources'],
      }"
    />
    <faq
      :data="{
        title: 'Your Questions Answered and then some',
        description:
          'At vero eos et accusamus et iusto odio dignissims ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores.',
        faqs: [
          {
            question:
              'Dignissim neque aliquet roin sed turpis et purus ultricies scelerisque',
            answer:
              'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in velit esse inline link cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.',
          },
          {
            question:
              'Et harum quidem rerum facilis est et expedita distinctio',
            answer:
              'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in velit esse inline link cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.',
          },
          {
            question: 'Nulla porta uma sit amet sagittis',
            answer:
              'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in velit esse inline link cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.',
          },
          {
            question:
              'Quos dolores et quas molestias excepturi sint occaecati cupiditate',
            answer:
              'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in velit esse inline link cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.',
          },
        ],
      }"
    />
    <slider
      style="margin-bottom: 16rem"
      :data="{
        title: 'Specialist Sectors',
      }"
    />
  </div>
</template>
<script>
import hero from '../components/hero/hero.vue';
import blog from '../components/posts/blog.vue';
import slider from '../components/slider/slider.vue';
import headline from '../components/atoms/headline.vue';
import testimonials from '../components/testimonials/testimonials.vue';
import faq from '../components/faq/faq.vue';
import benefits from '../components/benefits/benefits.vue';
  export default {
    components: {
      benefits,
      faq,
      testimonials,
      slider,
      blog,
      hero,
      headline,
    },
    transition: {
      name: 'slide-fade'
    },
  }
</script>
