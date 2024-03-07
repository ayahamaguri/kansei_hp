<template>
  <v-container>
    <h1 class="text-h4 font-weight-bold">Recruitment</h1>
    <div class="py-2" />
    <v-card flat>
      <v-card-title
        ><v-icon color="#fedd6b">mdi-star</v-icon>Message</v-card-title
      >
      <div style="margin: 0 40px">
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
      </div>
    </v-card>
    <div class="py-5" />

    <v-card class="rounded-card">
      <v-card-text>
        <v-simple-table style="white-space: pre-wrap">
          <tbody>
            <tr v-for="(item, index) in companyInfo" :key="index">
              <th>{{ item.header }}</th>
              <td>{{ addLineBreaks(item.body) }}</td>
            </tr>
          </tbody>
        </v-simple-table>
      </v-card-text>
    </v-card>
  </v-container>
</template>
<script lang="ts">
import { ref } from 'vue'

export default {
  setup() {
    const companyInfo = ref([
      {
        header: '職種',
        body: 'トラックドライバー（正社員）、配送業務（正社員）',
      },
      {
        header: '勤務時間',
        body: '0:00~9：00(休憩1時間あり)<br>(水)・(日)休日の週休二日制<br>※繫忙期のみ変則シフトあり',
      },
      {
        header: '給与',
        body: '日給1万円～1万3,000円',
      },
      {
        header: '必要な資格',
        body: '準中型免許以上（中型・大型免許お持ちの方大歓迎！）',
      },
      {
        header: '採用条件',
        body: '学歴・職歴不問。未経験OK！幅広い年代の方が活躍中！',
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

.rounded-card {
  border-radius: 25px; /* 丸い角の半径を指定 */
}
</style>
