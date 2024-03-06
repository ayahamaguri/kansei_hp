<template>
  <v-container>
    <h1 class="text-h4 font-weight-bold">お客様のNo.1企業を目指して</h1>
    <div class="py-2" />
    <!-- 左右に10pxの余白を持つ親要素 -->
    <div style="margin: 0 10px">
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
      <div class="py-5" />

      <v-simple-table style="white-space: pre-wrap">
        <tbody>
          <tr v-for="(item, index) in companyInfo" :key="index">
            <th>{{ item.header }}</th>
            <td>{{ addLineBreaks(item.body) }}</td>
          </tr>
        </tbody>
      </v-simple-table>
    </div>
  </v-container>
</template>
<script lang="ts">
import { ref } from 'vue'

export default {
  setup() {
    const companyInfo = ref([
      {
        header: '商号',
        body: '株式会社 関星',
      },
      {
        header: '所在地',
        body: '〒566-0062 大阪府摂津市鳥飼上4丁目3-7',
      },
      {
        header: 'TEL',
        body: '072-653-0880',
      },
      {
        header: 'FAX',
        body: '072-653-8118',
      },
      {
        header: '設立',
        body: '平成26年4月',
      },
      {
        header: '資本金',
        body: '3,000,000円',
      },
      {
        header: '代表',
        body: '濱口 美巨',
      },
      {
        header: '従業員数',
        body: '32名（パート含む）',
      },
      {
        header: '摂津倉庫',
        body: '〒566-0062 大阪府摂津市鳥飼上4丁目5-29',
      },
      {
        header: '事業内容',
        body: '各種メンテナンス業務<br>一般貨物自動車運送事業<br>貨物軽自動車運送事業<br>産業廃棄物収集運搬業',
      },
      {
        header: '車両台数',
        body: '大型貨物車両10台<br>中型貨物車両3台<br>小型貨物車両3台<br>軽貨物車両10台',
      },
      {
        header: '取引銀行',
        body: '北おおさか信用金庫 本店営業部<br>関西みらい銀行 茨木中央支店<br>京都中央信用金庫 高槻駅前支店<br>尼崎信用金庫 南茨木支店',
      },
    ])

    const addLineBreaks = (text: any) => {
      return text.replace(/<br\s*\/?>/g, '\n\r')
    }

    return {
      companyInfo,
      addLineBreaks,
    }
  },
}
</script>
<style scoped>
.v-simple-table >>> td {
  white-space: pre-wrap;
}
</style>
