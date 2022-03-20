<template>
  <div
    class="mx-6 my-6 max-w-[313px] pad:flex pad:flex-col pad:mx-10 pad:my-8 pad:max-w-none desktop:flex-row desktop:items-center desktop:justify-between desktop:mx-20 desktop:my-12 max:max-w-[1280px] max:mx-auto"
  >
    <div
      class="text-[#222222] font-semibold text-3xl mb-10 pad:text-4xl pad:max-w-[404px] desktop:mb-0"
    >
      {{ title }}
    </div>
    <Carousel
      :settings="settings"
      :breakpoints="breakpoints"
      class="pad:flex pad:flex-row pad:justify-between pad:w-full desktop:max-w-[717px]"
    >
      <Slide
        class="pad:w-1/2 pad:mr-20 desktop:max-w-[313px]"
        v-for="commercial in commercials"
        :key="commercial.id"
      >
        <div
          class="text-[#333333] text-2xl font-semibold mb-4 pad:max-w-[313px]"
        >
          {{ commercial.subtitle }}
        </div>
        <div class="text-[#484848] text-base pad:max-w-[313px]">
          {{ commercial.text }}
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
        itemsToShow: 2,
        snapAlign: 'center',
      },
    },
  }),
  setup() {
    const title = ref('Your Dream Destination: Be who you want to be')
    const commercials = reactive([
      {
        id: 1,
        subtitle: 'Metropolitan',
        text: 'One of the most diverse city in the world. Everything you need, find it here!',
      },
      {
        id: 2,
        subtitle: 'Isolate Islands',
        text: 'Get tired of busy life? Countless isolate islands for you escaping from reality.',
      },
    ])

    return {
      title,
      commercials,
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
