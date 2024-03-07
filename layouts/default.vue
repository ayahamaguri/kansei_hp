<template>
  <v-app>
    <v-app-bar flat app color="#003f67" dark>
      <v-row>
        <v-col v-if="isMobile" class="text-right">
          <v-btn icon @click="openModal">
            <v-icon>mdi-menu</v-icon>
          </v-btn>
          <v-dialog v-model="isModalOpen" width="300" height="500">
            <v-card class="pb-12">
              <!-- <v-row> -->
              <v-col class="d-flex justify-end">
                <v-card-actions>
                  <v-btn icon @click="closeModal">
                    <v-icon>mdi-close</v-icon>
                  </v-btn>
                </v-card-actions>
              </v-col>
              <!-- </v-row> -->
              <!-- <v-row> -->
              <v-col class="d-flex justify-center">
                <v-btn depressed color="#ffffff" to="/" @click="closeModal"
                  >ホーム</v-btn
                >
              </v-col>
              <!-- </v-row> -->
              <!-- <v-row> -->
              <v-col class="d-flex justify-center">
                <v-btn
                  depressed
                  color="#ffffff"
                  to="/company"
                  @click="closeModal"
                  >会社概要</v-btn
                >
              </v-col>
              <!-- </v-row> -->
              <!-- <v-row> -->
              <v-col class="d-flex justify-center">
                <v-btn
                  depressed
                  color="#ffffff"
                  to="/service"
                  @click="closeModal"
                  >サービス</v-btn
                >
              </v-col>
              <!-- </v-row> -->
              <!-- <v-row> -->
              <v-col class="d-flex justify-center">
                <v-btn
                  depressed
                  color="#ffffff"
                  to="/recruit"
                  @click="closeModal"
                  >採用情報</v-btn
                >
              </v-col>
              <!-- </v-row> -->
            </v-card>
          </v-dialog>
        </v-col>

        <v-col v-else class="d-flex flex-row justify-center">
          <v-btn depressed color="#003f67" to="/">ホーム</v-btn>
          <v-btn depressed color="#003f67" to="/company">会社概要</v-btn>
          <v-btn depressed color="#003f67" to="/service">サービス</v-btn>
          <v-btn depressed color="#003f67" to="/recruit">採用情報</v-btn>
        </v-col>
      </v-row>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer color="#003f67" dark>
      <v-row justify="center" no-gutters>
        <v-col class="text-center mt-4" cols="12">
          2020Ⓒ <strong>株式会社関星 KANSAI STAR LINE</strong> All Rights
          Reserved.
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
import { onBeforeUnmount, onMounted, ref } from 'vue'

export default {
  name: 'DefaultLayout',
  setup() {
    const isMobile = ref(window.innerWidth <= 600)
    const handleResize = () => {
      isMobile.value = window.innerWidth <= 600
    }

    onMounted(() => {
      window.addEventListener('resize', handleResize)
    })

    onBeforeUnmount(() => {
      window.removeEventListener('resize', handleResize)
    })

    const isModalOpen = ref(false)
    const openModal = () => {
      isModalOpen.value = true
    }
    const closeModal = () => {
      isModalOpen.value = false
    }

    return {
      isMobile,
      drawer: false,
      isModalOpen,
      openModal,
      closeModal,
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
