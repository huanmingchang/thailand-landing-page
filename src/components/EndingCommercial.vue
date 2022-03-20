<template>
  <div>
    <div
      class="max-w-[1280px] flex flex-col justify-center mx-auto px-6 h-[544px] mobile:h-[684px] pad:h-[541px] pad:px-10 desktop:px-20 bg-[url('/src/assets/_MG_3509.jpeg')] bg-no-repeat bg-cover"
    >
      <div class="text-[32px] font-extrabold text-[#fff] pad:text-[42px]">
        {{ mainTitle }}
      </div>
      <div class="text-base text-[#fff] mt-2 mb-6 pad:text-lg pad:mt-4">
        {{ subTitle }}
      </div>
      <div class="h-14 mobile:mb-16 pad:mb-0">
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
    const mainTitle = ref('Your second home is waiting')
    const subTitle = ref('This is what you dream about every night')
    const button = reactive({
      text: 'Fly now!',
      link: 'https://www.skyscanner.com.tw/flights-to/bkkt/cheap-flights-to-bangkok.html',
    })

    return {
      mainTitle,
      subTitle,
      button,
    }
  },
}
</script>

<style lang="postcss" scoped>
.btn:hover {
  transform: scale(1.05);
}

.btn:active {
  transform: scale(1);
  box-shadow: inset 0 0 10px 1px rgba(0, 0, 0, 0.2);
}
</style>
