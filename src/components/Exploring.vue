<template>
  <div
    class="max-w-[1280px] h-[544px] my-6 mx-0 mobile:h-[684px] pad:h-[464px] pad:my-8 pad:mx-10 pad:rounded-2xl desktop:my-12 desktop:mx-20 max:mx-auto"
  >
    <div
      class="flex flex-col justify-evenly w-full h-full pad:rounded-2xl bg-[url('/public/IMG_0289.jpeg')] bg-no-repeat bg-cover"
    >
      <div class="text-xs font-bold text-[#fff] px-6 pad:text-lg">
        {{ slogan }}
      </div>
      <div
        class="text-3xl font-bold text-[#fff] px-6 leading-[42px] mobile:max-w-[258px] pad:max-w-[466px] pad:text-[42px] pad:leading-[54.8px]"
      >
        {{ mainTitle }}
      </div>
      <div class="h-14 px-6">
        <a :href="button.link" target="_blank" class="w-[90px] h-full">
          <button
            class="btn h-full py-4 px-8 rounded-lg bg-[#E61E4D] text-[#fff] cursor-pointer"
          >
            {{ button.text }}
          </button>
        </a>
      </div>
    </div>
  </div>
</template>
<script>
import { ref, reactive } from 'vue'
export default {
  setup() {
    const slogan = ref('Amazing Thailand')
    const mainTitle = ref('Exploring life, exploring possibilities')
    const button = reactive({
      text: 'Take me there!',
      link: 'https://www.kkday.com/zh-tw/city/bangkok',
    })

    return {
      slogan,
      mainTitle,
      button,
    }
  },
}
</script>

<style lang="postcss" scoped>
.btn:hover {
  @apply scale-105;
}

.btn:active {
  @apply scale-105 shadow-2xl;
}
</style>
