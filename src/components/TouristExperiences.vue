<template>
  <div
    class="flex flex-col rounded-2xl mx-6 my-6 pad:flex-row pad:items-center pad:h-[471px] pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 desktop:max-w-[1280px] max:mx-auto bg-[#f7f7f7]"
  >
    <div
      class="bg-[url('https://i.pravatar.cc/600?img=5')] bg-no-repeat bg-cover rounded-t-2xl h-[216px] pad:rounded-l-2xl pad:rounded-tr-none pad:h-full pad:w-1/2"
    ></div>
    <div class="flex flex-col px-16 py-10 pad:py-8 pad:w-1/2">
      <div class="text-lg mb-4 text-black pad:text-2xl">
        [I think Bangkok and all another place in thailand have nice, beautiful,
        interresting, relaxing, tasty, friendly and many more parts and
        place.... Up to you what you like to do....]
      </div>
      <div class="text-sm text-black pad:text-base">Catherine</div>
      <div class="text-sm text-black mb-4 pad:text-base">California</div>
      <div class="font-semibold text-sm text-black">
        <a
          href=""
          target="_blank"
          class="cursor-pointer hover:underline hover:decoration-solid"
          >See profile</a
        >
      </div>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
  setup() {
    const users = reactive([
      {
        id: 1,
        avatar: 'https://i.pravatar.cc/600?img=5',
        text: 'I think Bangkok and all another place in thailand have nice, beautiful, interresting, relaxing, tasty, friendly and many more parts and place.... Up to you what you like to do....',
        name: 'Catherine',
        from: 'California, United States',
      },
      {
        id: 2,
        avatar: 'https://i.pravatar.cc/600?img=10',
        text: 'I loved it, Bangkok has so much hidden gems like this ! A must see in Bangkok, try to come early morning to avoid the groups...',
        name: 'Amanda',
        from: 'Paris, France',
      },
      {
        id: 3,
        avatar: 'https://i.pravatar.cc/600?img=12',
        text: 'There are some other wonderful beaches on this Island but this one is a sure bet, especially with some of the best resorts located right on it.',
        name: 'Andrew',
        from: 'London, Britain',
      },
      {
        id: 4,
        avatar: 'https://i.pravatar.cc/600?img=17',
        text: 'we loved this beach and also white sands but we preferred white sands because it had too many options for bar restaurants shop around the beach. ',
        name: 'Robert',
        from: 'Georgia, United States',
      },
      {
        id: 5,
        avatar: 'https://i.pravatar.cc/600?img=20',
        text: 'Places to see, ways to wander, and signature experiences.',
        name: 'Mia',
        from: 'Warsaw, Poland',
      },
    ])
  },
}
</script>
