<template>
  <div>
    <div class="flex justify-between px-4 pt-4">
      <nuxt-img class="w-8 h-full" src="/icon.png"></nuxt-img>
      <toggle-theme></toggle-theme>
    </div>
    <!-- <div class="w-full h-full grid grid-cols-2" v-if="imageSrc">
    </div> -->


    <nuxt-img v-show="colorMode.value === 'dark'"
      :src="`https://res.cloudinary.com/ddc0cce3m/image/upload/v1695676230/CricaDev/darkMode-cricadev_qxqwee.png`"
      class="home-image" alt="" />
    <nuxt-img v-show="colorMode.value === 'light'"
      :src="`https://res.cloudinary.com/ddc0cce3m/image/upload/v1695676230/CricaDev/lightMode-cricadev_hbe5l6.png`"
      class="home-image" alt="" />

    <div class="flex gap-2 absolute bottom-16  px-8 justify-center cricadev-letters">
      <nuxt-img provider="cloudinary" src="/C_ukccuh.png" alt="" class="c-1 letter" />
      <nuxt-img provider="cloudinary" src="/R_nd1wdg.png" alt="" class="r-1 letter" />
      <nuxt-img provider="cloudinary" src="/I_lno1vl.png" alt="" class="i-1 letter" />
      <nuxt-img provider="cloudinary" src="/C_ukccuh.png" alt="" class="c letter" />
      <nuxt-img provider="cloudinary" src="/A_zy0fy4.png" alt="" class="a letter" />
      <nuxt-img provider="cloudinary" src="/D_jy2cjg.png" alt="" class="d letter" />
      <nuxt-img provider="cloudinary" src="/E_suquw4.png" alt="" class="e letter" />
      <nuxt-img provider="cloudinary" src="/V_gm7moy.png" alt="" class="v letter" />
    </div>
    <!--   <nuxt-img class="home-image" provider="cloudinary" :src="imageSrc"></nuxt-img> -->
  </div>
</template>

<script setup>
// import { useWindowSize } from '@vueuse/core'
const colorMode = useColorMode();
//declarations
// const { width } = useWindowSize();


// //reactive values
// const isMobile = computed(() => {
//   return width.value < 600;
// });




</script>

<style lang="scss">
@import 'assets/styles/index.scss';

body {
  @apply bg-[var(--white)] dark:bg-[var(--black)];
}

.home-image {
  @apply w-full h-auto absolute bottom-0 left-0 object-cover object-center pointer-events-none lg:w-[50%] lg:h-full;
  animation: slideUp 1s ease-in forwards;
  animation-delay: 1s;

  @keyframes slideUp {
    0% {
      transform: scale(1) translateY(0%);
    }

    100% {
      transform: scale(1.5) translateY(-10%) translateX(10%);
    }
  }
}

.cricadev-letters {
  transform: translateY(100%);

  animation: fadeUp 1s ease-in forwards;
  animation-delay: 1s;

  @keyframes fadeUp {
    0% {
      transform: translateY(100%);
    }

    100% {
      transform: translateY(0%)
    }
  }
}
</style>