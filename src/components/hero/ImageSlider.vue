<template>
  <div>
    <!-- {{ JSON.stringify(product_categories, undefined, 1) }} -->
    <Swiper
      :slides-per-view="1"
      :space-between="50"
      :navigation="true"
      @swiper="onSwiper"
      @slideChange="con"
    >
      <SwiperSlide
        class="py-20"
        v-for="item in product_categories"
        :key="item.name"
      >
        <div class="container-xl">
          <h1 class="title">{{ item.name }}</h1>
          <div class="subtitle balance py2">this is a test</div>
        </div>
      </SwiperSlide>
    </Swiper>
  </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/navigation";
import "swiper/css/autoplay";

// import required modules
import { Navigation, Autoplay } from "swiper/modules";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: ["product_categories"],
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      modules: [Navigation, Autoplay],
      onSwiper,
      onSlideChange,
    };
  },
  mounted() {
    console.log(this.props);
  },
};
</script>
