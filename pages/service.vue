<template>
  <v-container>
    <v-card flat>
      <v-card-title
        ><v-icon color="#fedd6b">mdi-star</v-icon>Service</v-card-title
      >
      <div style="margin: 0 40px">
        <div>
          お客様の満足向上のため、絶えず想像し挑戦する会社であり続けます。
        </div>
        <div>
          お客様をサポートする最良のパートナーを目指し、ベストサ－ビス・ベストプロダクトを提供します。
        </div>
        <div>
          まだまだ未熟な私共ですが、関係する方々との信頼関係を構築し、今後も邁進していく所存でございます。
        </div>
        <div>ご愛顧・ご支援のほど、よろしくお願い申し上げます。</div>
      </div>
      <div class="py-5" />
    </v-card>
    <v-card flat class="rounded-card" color="#4f85a6" dark>
      <v-img :src="require('@/assets/root.png')" height="250"></v-img>
      <v-card-title>自動車運送事業</v-card-title>
      <v-card-text
        >効率的かつ信頼性の高い物流サービスを提供しています。<br />長年の経験を基に、輸送ニーズに柔軟かつ迅速に対応し、安全性と効率性を両立させ、お客様のビジネスにおける成功を支えています。</v-card-text
      >
    </v-card>
    <div class="py-2" />
    <v-card flat class="rounded-card" color="#0054a7" dark>
      <v-img :src="require('@/assets/side_gray.png')" height="250"></v-img>
      <v-card-title>中古車販売事業</v-card-title>
      <v-card-text
        >高品質かつ信頼性のある中古車を提供しています。<br />豊富な在庫と専門的な知識を活かし、お客様のニーズに合った車両をご提案いたします。</v-card-text
      >
    </v-card>
  </v-container>
</template>
<style scoped>
.rounded-card {
  border-radius: 25px; /* 丸い角の半径を指定 */
}
</style>
