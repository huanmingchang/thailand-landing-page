<template>
  <div
    class="my-6 px-6 max-w-[313px] md:flex md:flex-col md:max-w-[100vw] md:my-8 md:px-10 lg:flex-row lg:items-center lg:justify-between lg:max-w-[1280px] lg:my-12 lg:px-20 lg:mx-auto"
  >
    <div
      class="text-[#222222] font-semibold text-3xl mb-10 md:text-4xl md:max-w-[404px] lg:mb-0"
    >
      {{ title }}
    </div>
    <div
      class="md:flex md:flex-row md:justify-between md:w-full lg:max-w-[717px]"
    >
      <div
        class="md:w-1/2 md:mr-4 lg:max-w-[313px]"
        v-for="commercial in commercials"
        :key="commercial.id"
      >
        <div
          class="text-[#333333] text-2xl font-semibold mb-4 md:max-w-[313px]"
        >
          {{ commercial.subtitle }}
        </div>
        <div class="text-[#484848] text-base md:max-w-[313px]">
          {{ commercial.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
export default {
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
}
</script>
