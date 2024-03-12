<template>
  <div class="background-image-container">
    <v-container class="fill-height">
      <v-responsive class="align-center text-center fill-height">
        <!-- <div v-if="isMobile" class="py-5" /> -->
        <!-- <img
          v-if="isMobile"
          class="slide-up-animation"
          height="100"
          src="@/assets/logo_title_msg_isMobile3.png"
        /> -->
        <div v-if="isMobile" class="vertical-stack">
          <img
            class="slide-up-animation"
            width="200"
            src="@/assets/message.png"
          />
          <img height="100" src="@/assets/starLogo.png" />
          <img
            class="slide-up-animation"
            height="50"
            width="200"
            src="@/assets/companyName.png"
          />
        </div>
        <div v-else class="image-container">
          <img
            class="slide-up-animation"
            height="50"
            width="700"
            src="@/assets/message.png"
          />
          <div class="bottom-row">
            <img height="150" src="@/assets/starLogo.png" />
            <img
              class="slide-up-animation"
              height="150"
              width="600"
              src="@/assets/companyName.png"
            />
          </div>
        </div>
      </v-responsive>
    </v-container>
  </div>
</template>

<script>
import { onBeforeUnmount, onMounted, ref } from 'vue'
export default {
  name: 'IndexPage',

  setup() {
    const isMobile = ref(window.innerWidth <= 1250)
    const handleResize = () => {
      isMobile.value = window.innerWidth <= 1250
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

.slide-up-animation {
  animation: slideUp 3s ease;
  /* opacity: 0; /* 初期状態では透明にしておく */
}

@keyframes slideUp {
  from {
    transform: translateY(100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.image-container {
  display: flex;
  flex-direction: column;
  align-items: center; /* 中央揃え */
}

.bottom-row {
  display: flex;
  justify-content: space-around; /* 画像の間隔を均等に配置 */
}

.vertical-stack {
  display: flex;
  flex-direction: column;
  align-items: center; /* 中央揃え */
}
</style>
