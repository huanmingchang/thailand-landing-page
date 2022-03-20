<template>
  <div
    class="max-w-[1280px] flex flex-col mx-6 my-6 pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 max:mx-auto"
  >
    <div
      class="mb-9 font-extrabold text-[32px] text-[#333333] pad:mb-[46px] pad:text-[46px]"
    >
      Experiences
    </div>
    <Carousel
      :settings="settings"
      :breakpoints="breakpoints"
      class="flex flex-row justify-between"
    >
      <Slide
        v-for="experience in experiences"
        :key="experience.id"
        class="flex flex-col justify-start items-start w-1/4 pad:mr-8"
      >
        <div class="mb-4 text-2xl font-semibold text-[#222222]">
          {{ experience.title }}
        </div>
        <div class="mb-4 text-base text-[#484848]">
          {{ experience.text }}
        </div>
        <div>
          <a
            :href="experience.link"
            target="_blank"
            class="text-base font-semibold text-[#333333] underline cursor-pointer"
          >
            Know more about...</a
          >
        </div>
      </Slide>
    </Carousel>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide, Pagination } from 'vue3-carousel'
import './../assets/carousel.css'

export default defineComponent({
  components: {
    Pagination,
    Carousel,
    Slide,
    Navigation,
  },
  data: () => ({
    // carousel settings
    settings: {
      itemsToShow: 1,
      snapAlign: 'center',
    },
    // breakpoints are mobile first
    // any settings not specified will fallback to the carousel settings
    breakpoints: {
      743: {
        itemsToShow: 3,
        snapAlign: 'center',
      },
    },
  }),
  setup() {
    const experiences = reactive([
      {
        id: 1,
        title: 'Spa',
        text: 'Experience a traditional Thai massage. Immerse yourself in the peaceful and serene atmosphere',
        link: 'https://www.kkday.com/zh-tw/product/10393',
      },
      {
        id: 2,
        title: 'One Day Tour',
        text: 'Experience authentic Thai culture on a private day tour in Bangkok.Discover intriguing flavors and sample local snacks at floating market',
        link: 'https://www.kkday.com/zh-tw/product/21746',
      },
      {
        id: 3,
        title: 'Outdoor',
        text: '30 to 35 km bike trip exploring Bangkok. Professional English tour guide suitable for all ages.',
        link: 'https://www.kkday.com/zh-tw/product/8869',
      },
    ])

    return {
      experiences,
    }
  },
})
</script>

<style lang="postcss" scoped>
.carousel {
  margin: 0;
  width: 100%;
}
</style>
