<template>
  <div class="background-image-container">
    <v-container class="fill-height">
      <v-responsive class="align-center text-center fill-height">
        <div v-if="isMobile" class="py-5" />
        <img v-if="isMobile" height="100" src="@/assets/logo2.svg" />
        <div v-if="isMobile" class="py-5" />
        <img v-else height="300" width="1200" src="@/assets/logo2.svg" />

        <h1
          v-if="isMobile"
          class="text-h3 font-weight-bold"
          style="color: #f5f3f2"
        >
          株式会社関星
        </h1>
        <h1
          v-else
          class="text-h2 font-weight-bold custom-font"
          style="color: #f5f3f2; font-family: 'CustomFont', sans-serif"
        >
          株式会社関星
        </h1>
      </v-responsive>
    </v-container>
  </div>
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
<style scoped>
.background-image-container {
  background-image: url('@/assets/root_bg.jpg'); /* 画像のパスを正しく指定する */
  background-size: cover;
  background-position: center;
  height: 100vh; /* 画面の高さの85%に調整 */
  width: 100vw; /* 画面の幅の90%に調整 */
  margin: 0; /* 中央寄せのために追加 */
}
/* スマホ版のスタイル */
@media screen and (max-width: 600px) {
  .text-right {
    text-align: right; /* 右寄せ */
  }
}

@font-face {
  font-family: 'CustomFont';
  src: url('../assets/fonts/Ronde-B_square.otf') format('opentype');
}

.custom-font {
  font-family: 'CustomFont', sans-serif; /* 'sans-serif'はフォントが読み込まれない場合のフォールバックフォント */
}
</style>
