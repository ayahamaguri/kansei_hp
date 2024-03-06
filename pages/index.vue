<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <div v-if="isMobile" class="py-5" />
      <img v-if="isMobile" height="100" src="@/assets/Star_logo2.svg" />
      <div v-if="isMobile" class="py-5" />

      <img v-else height="300" src="@/assets/Star_logo2.svg" />

      <div class="text-body-1 font-weight-light">KANSAI STAR LINE</div>

      <h1 class="text-h3 font-weight-bold">株式会社関星</h1>
    </v-responsive>
  </v-container>
</template>

<script>
import { onBeforeUnmount, onMounted, ref } from 'vue'
export default {
  name: 'IndexPage',

  setup() {
    const isMobile = ref(window.innerWidth <= 1100)
    const handleResize = () => {
      isMobile.value = window.innerWidth <= 1100
    }
    onMounted(() => {
      window.addEventListener('resize', handleResize)
    })

    onBeforeUnmount(() => {
      window.removeEventListener('resize', handleResize)
    })

    return {
      isMobile,
    }
  },
}
</script>
<style>
/* スマホ版のスタイル */
@media screen and (max-width: 600px) {
  .text-right {
    text-align: right; /* 右寄せ */
  }
}
</style>
