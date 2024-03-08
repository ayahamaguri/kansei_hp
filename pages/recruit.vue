<template>
  <v-container>
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
              <td>
                <!-- v-ifで文字列に"http"が含まれている場合はハイパーリンクにする -->
                <template v-if="item.body.includes('http')">
                  <a :href="item.body" target="_blank">{{
                    addLineBreaks(item.body)
                  }}</a>
                </template>
                <!-- それ以外の場合はそのまま表示 -->
                <template v-else> {{ addLineBreaks(item.body) }}</template>
              </td>
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
        header: '応募資格・条件',
        body: '学歴・職歴不問。未経験可<br>※準中型免許以上必須（中型・大型免許お持ちの方大歓迎！）',
      },
      {
        header: '勤務地',
        body: '株式会社 関星<br>大阪府摂津市鳥飼上4-3-7<br>車通勤可',
      },
      {
        header: '勤務時間',
        body: '変形労働時間制<br>想定労働時間 8時間/日<br>【シフト例】<br>・6：00-17：00<br>・7：00-18：00<br>・0：00-7：00<br>※繫忙期のみ変則シフトあり',
      },
      {
        header: '給与',
        body: '日給1万円～1万3,000円<br>※経験・能力を考慮して決定します。',
      },
      {
        header: '福利厚生',
        body: '雇用保険、厚生年金、健康保険、労災保険',
      },
      {
        header: 'ご応募はこちらから',
        body: 'https://en-gage.net/kansaistar_saiyo/',
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
