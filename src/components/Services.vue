<template>
  <div
    class="max-w-[1280px] flex flex-col mx-6 my-6 pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 max:mx-auto"
  >
    <div
      class="mb-9 font-extrabold text-[32px] text-[#333333] pad:mb-[46px] pad:text-[46px]"
    >
      Experiences
    </div>
    <div class="flex flex-row justify-between">
      <div
        v-for="experience in experiences"
        :key="experience.id"
        class="flex flex-col w-1/4"
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
      </div>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
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
}
</script>
