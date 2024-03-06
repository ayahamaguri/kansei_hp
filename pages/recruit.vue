<template>
  <v-container>
    <h1 class="text-h4 font-weight-bold">Recruitment</h1>
    <div class="py-2" />
    <!-- 左右に10pxの余白を持つ親要素 -->
    <div style="margin: 0 10px">
      <div>
        少子高齢化社会が確実に到来し、近未来における労働力人口問題は、今後ますます深刻化していきそうです。
      </div>
      <div>
        企業の人材に対しての考えや、労働者がライフワークの中で職を求め働くという価値観はその立場により様々です。
      </div>
      <div>
        また、刻々と変化する社会で、企業の人材への期待や求める内容も大きく変化しています。
      </div>
      <div>
        弊社は、生き生きと働き喜びを感じる人とのコミュニケーションを大切にしていきたいと願っております。
      </div>
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
        header: '職種',
        body: '',
      },
      {
        header: '勤務時間',
        body: '平日　11:30～23:00（時間交代制）<br>休日　10:30～23:00（時間交代制）',
      },
      {
        header: '給与',
        body: '1,100円～（研修期間/1,050円）<br>土日祝 100円UP<br>GW・お盆・年末年始 200円UP',
      },
      {
        header: '待遇',
        body: 'アルバイト（シフト制）<br>※未成年者は保護者の同意が必要<br>制服貸与、交通費月１万円迄支給',
      },
      {
        header: '加入保険等',
        body: '雇用保険・健康保険加入制度あり',
      },
      {
        header: '採用条件',
        body: '1）心身ともに健康な方<br>2）長期勤務出来る方<br>3）土日祝入れる方',
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
