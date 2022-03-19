<template>
  <carousel>
    <slide
      v-for="user in users"
      :key="user.id"
      :id="user.id"
      class="flex flex-col rounded-2xl mx-6 my-6 pad:flex-row pad:items-center pad:h-[471px] pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 desktop:max-w-[1280px] max:mx-auto bg-[#f7f7f7] relative"
    >
      <div
        :class="user.avatar"
        class="bg-no-repeat bg-cover rounded-t-2xl h-[216px] pad:rounded-l-2xl pad:rounded-tr-none pad:h-full pad:w-1/2"
      ></div>
      <div class="flex flex-col px-16 py-10 pad:py-8 pad:w-1/2">
        <div class="text-lg mb-4 text-black pad:text-2xl">
          {{ '"' + user.text + '"' }}
        </div>
        <div class="text-sm text-black pad:text-base">{{ user.name }}</div>
        <div class="text-sm text-black mb-4 pad:text-base">{{ user.from }}</div>
        <div class="font-semibold text-sm text-black">
          <a
            target="_blank"
            class="cursor-pointer hover:underline hover:decoration-solid"
            >See profile</a
          >
        </div>
      </div>
    </slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </carousel>
</template>

<script>
import { ref, reactive } from 'vue'
import { defineComponent } from 'vue'
import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'
import './../assets/carousel.css'

export default defineComponent({
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  setup() {
    const users = reactive([
      {
        id: 1,
        avatar: 'bg-[url(/public/Catherine.jpeg)]',
        text: 'I think Bangkok and all another place in thailand have nice, beautiful, interresting, relaxing, tasty, friendly and many more parts and place...',
        name: 'Catherine',
        from: 'California, United States',
      },
      {
        id: 2,
        avatar: 'bg-[url(/public/Amanda.jpeg)]',
        text: 'I loved it, Bangkok has so much hidden gems like this ! A must see in Bangkok, try to come early morning to avoid the groups...',
        name: 'Amanda',
        from: 'Paris, France',
      },
      {
        id: 3,
        avatar: 'bg-[url(/public/Andrew.jpeg)]',
        text: 'There are some other wonderful beaches on this Island but this one is a sure bet, especially with some of the best resorts located right on it.',
        name: 'Andrew',
        from: 'London, Britain',
      },
      {
        id: 4,
        avatar: 'bg-[url(/public/Robert.jpeg)]',
        text: 'we loved this beach and also white sands but we preferred white sands because it had too many options for bar restaurants shop around the beach. ',
        name: 'Robert',
        from: 'Georgia, United States',
      },
      {
        id: 5,
        avatar: 'bg-[url(/public/Mia.jpeg)]',
        text: 'Places to see, ways to wander, and signature experiences.',
        name: 'Mia',
        from: 'Warsaw, Poland',
      },
    ])

    return {
      users,
    }
  },
})
</script>
