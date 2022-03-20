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
        img: '/public/27.jpg',
        name: 'Bua Loy Bingsu',
      },
      {
        id: 2,
        img: '/public/31.jpg',
        name: 'Meatball',
      },
      {
        id: 3,
        img: '/public/34.jpg',
        name: 'Seafood with coconut',
      },
      {
        id: 4,
        img: '/public/39.jpg',
        name: 'Krapaw Moo',
      },
      {
        id: 5,
        img: '/public/59.jpg',
        name: 'Kao Man Gai',
      },
      {
        id: 6,
        img: '/public/60.jpg',
        name: 'Kai Luk Khey',
      },
      {
        id: 7,
        img: '/public/62.jpg',
        name: 'Chim Chum',
      },
      {
        id: 8,
        img: '/public/64.jpg',
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
