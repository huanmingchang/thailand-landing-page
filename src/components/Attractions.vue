<template>
  <div
    class="flex flex-col max-w-[1280px] my-6 mx-12 pad:mx-10 pad:my-8 desktop:mx-20 desktop:my-12 max:mx-auto"
  >
    <div class="text-[26px] text-[#222222] font-extrabold mb-6 pad:text-[42px]">
      Attractions
    </div>
    <div class="flex flex-row justify-between bg-[#f7f7f7]">
      <Carousel :settings="settings" :breakpoints="breakpoints">
        <Slide
          v-for="attraction in attractions"
          :key="attraction.id"
          class="flex flex-col"
        >
          <div class="w-[250px] h-[260px] rounded-lg">
            <img
              :src="attraction.img"
              alt=""
              class="w-[250px] h-[260px] rounded-lg"
            />
          </div>
          <a :href="attraction.map" target="_blank">
            <div
              class="text-lg text-[#222222] font-extrabold pad:text-xl hover:underline"
            >
              {{ attraction.name }}
            </div></a
          >

          <div class="text-sm text-[#222222] mt-2">
            {{ attraction.location }}
          </div>
        </Slide>
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
    const attractions = reactive([
      {
        id: 1,
        img: '/public/54.jpg',
        name: 'Wat Palad',
        location: 'Chiang Mai',
        map: 'https://www.google.com/maps/place/Wat+Pha+Lat/@18.7993968,98.9319581,17z/data=!3m1!4b1!4m5!3m4!1s0x30da3a1a20f4a0eb:0x5def9b5b34bb6888!8m2!3d18.7993968!4d98.9341468',
      },
      {
        id: 2,
        img: '/public/55.jpg',
        name: 'Doi Suthep',
        location: 'Chiang Mai',
        map: 'https://www.google.com/maps/place/Wat+Phra+That+Doi+Suthep,+Ratchaworawihan/@18.7993966,98.9253652,15z/data=!4m9!1m2!2m1!1sDoi+Suthep!3m5!1s0x30da39b5dff1ddb5:0x9d864c5caec57e21!8m2!3d18.8049889!4d98.9216337!15sCgpEb2kgU3V0aGVwWgwiCmRvaSBzdXRoZXCSAQ9idWRkaGlzdF90ZW1wbGWaASNDaFpEU1VoTk1HOW5TMFZKUTBGblNVTkhNRTVFT0VSbkVBRQ',
      },
      {
        id: 3,
        img: '/public/56.jpg',
        name: 'Wat Umong',
        location: 'Chiang Mai',
        map: 'https://www.google.com/maps/place/Wat+Umong/@18.7861936,98.9530176,14z/data=!4m9!1m2!2m1!1sWat+Umong!3m5!1s0x30da3a706f40689d:0xedef9aa39d595059!8m2!3d18.7833134!4d98.9511902!15sCglXYXQgVW1vbmdaCyIJd2F0IHVtb25nkgEPYnVkZGhpc3RfdGVtcGxl',
      },
      {
        id: 4,
        img: '/public/57.jpg',
        name: 'Wat Ton Kwaen',
        location: 'Chiang Mai',
        map: 'https://www.google.com/maps/place/Wat+Intharawat+(Wat+Ton+Kwen)/@18.7228396,98.9231836,17z/data=!3m1!4b1!4m5!3m4!1s0x30da3132a3414f5b:0x715c4af352507102!8m2!3d18.7228312!4d98.9253758',
      },
    ])

    return {
      attractions,
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
