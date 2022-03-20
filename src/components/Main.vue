<template>
  <div>
    <div
      class="max-w-[1280px] flex flex-col justify-center pb-16 px-6 mx-auto h-[544px] mobile:justify-end mobile:h-[684px] mobile:pb-0 pad:justify-center pad:h-[541px] pad:px-10 desktop:px-20 bg-[url('/public/IMG_0513.JPG')] bg-no-repeat bg-cover"
    >
      <div class="text-xs font-bold text-[#fff] mb-3 pad:text-lg">
        {{ slogan }}
      </div>
      <div class="text-3xl font-bold text-[#fff] mb-4 pad:text-6xl">
        {{ mainTitle }}
      </div>
      <div class="text-base text-[#fff] mb-4 pad:text-xl">
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
  // TODO 修改背景圖片超過 1280px 的效果
  setup() {
    const slogan = ref('Amazing Thailand')
    const mainTitle = ref('Reopen, Revive, Revisit')
    const subTitle = ref('Do you miss me? I miss you so much!')
    const button = reactive({
      text: 'Take me there!',
      link: 'https://www.skyscanner.com.tw/flights-to/bkkt/cheap-flights-to-bangkok.html',
    })

    return {
      slogan,
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
