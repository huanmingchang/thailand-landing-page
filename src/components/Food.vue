<template>
  <div
    class="flex flex-col max-w-[1280px] my-6 mx-12 pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 max:mx-auto"
  >
    <div class="text-[32px] text-[#222222] font-extrabold mb-6 pad:text-[46px]">
      Food
    </div>
    <div class="flex flex-row justify-between">
      <Carousel :settings="settings" :breakpoints="breakpoints">
        <Slide
          v-for="food in foodCollection"
          :key="food.id"
          class="flex flex-col"
        >
          <div class="w-[250px] h-[260px] rounded-lg">
            <img
              :src="food.img"
              alt=""
              class="w-[250px] h-[260px] rounded-lg shadow-md shadow-slate-300"
            />
          </div>
          <div class="text-lg text-[#222222] font-extrabold mt-4 pad:text-xl">
            {{ food.name }}
          </div>
        </Slide>

        <template #addons>
          <Navigation />
        </template>
      </Carousel>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide, Pagination } from 'vue3-carousel'
import './../styles/carousel.css'
import image27 from '../assets/27.jpg'
import image31 from '../assets/31.jpg'
import image34 from '../assets/34.jpg'
import image39 from '../assets/39.jpg'
import image59 from '../assets/59.jpg'
import image60 from '../assets/60.jpg'
import image62 from '../assets/62.jpg'
import image64 from '../assets/64.jpg'

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
      670: {
        itemsToShow: 2,
        snapAlign: 'start',
      },
      990: {
        itemsToShow: 3,
        snapAlign: 'start',
      },
      1240: {
        itemsToShow: 4,
        snapAlign: 'center',
      },
    },
  }),
  setup() {
    const foodCollection = reactive([
      {
        id: 1,
        img: image27,
        name: 'Bua Loy Bingsu',
      },
      {
        id: 2,
        img: image31,
        name: 'Meatball',
      },
      {
        id: 3,
        img: image34,
        name: 'Seafood with coconut',
      },
      {
        id: 4,
        img: image39,
        name: 'Krapaw Moo',
      },
      {
        id: 5,
        img: image59,
        name: 'Kao Man Gai',
      },
      {
        id: 6,
        img: image60,
        name: 'Kai Luk Khey',
      },
      {
        id: 7,
        img: image62,
        name: 'Chim Chum',
      },
      {
        id: 8,
        img: image64,
        name: 'Moo Bing',
      },
    ])

    return {
      foodCollection,
    }
  },
})
</script>

<style lang="postcss" scoped>
.carousel {
  @apply m-0 w-full;
}
</style>
