<template>
  <div>
    <h3>最終更新：{{ releases[releases.length - 1].timestamp }}</h3>
    <el-collapse v-model="releaseNote">
      <el-collapse-item title="更新履歴">
        <el-timeline :reverse="true">
          <el-timeline-item
              v-for="(release, index) in releases"
              :key="index"
              :timestamp="release.timestamp">
            <div v-html="release.content"></div>
          </el-timeline-item>
        </el-timeline>
      </el-collapse-item>
    </el-collapse>
  </div>
</template>

<script>
export default {
  name: "ReleaseNote",
  data: function () {
    return {
      releaseNote: '',
      releases: [
        {
          content: 'αリリース',
          timestamp: '2021-06-07'
        },
        {
          content: 'コースデータを補完、ゲームデータ上の坂判定を適用、掛かりと出遅れ実装（ついでにブルボンの固有発動条件も）、コースのステータスチェック実装',
          timestamp: '2021-06-09'
        },
        {
          content: 'セイウンスカイの固有更新、固有スキルを独立化してレベル設定できるようにして補完、緑とゲートスキル実装',
          timestamp: '2021-06-10'
        },
        {
          content: 'パッシブスキルが確定発動じゃないバグを修正',
          timestamp: '2021-06-11'
        },
        {
          content: '色々とスキルバグを修正、どこか発動スキルの10m余裕を修正、直線ランダムスキルを修正、コーナーを表記するようになった。緑スキルのバグを修正した。',
          timestamp: '2021-06-12'
        },
        {
          content: '坂の影響が正しくなかったバグを修正',
          timestamp: '2021-06-13'
        },
        {
          content: '賢さによるランダム速度の式を修正',
          timestamp: '2021-06-17'
        },
        {
          content: '直線コースがバグったのを修正',
          timestamp: '2021-06-19'
        },
        {
          content: '競技場エミュレーターを追加。季節や天候の比例は見かけたものと自前のデータを参考にしてふわっと定めました。各々の確率は緑スキルに記載。<br>新潟1000mがバグる問題修正',
          timestamp: '2021-06-20'
        },
        {
          content: 'コース毎の最小及び最大タイムを表記、他色々細かいバグ修正',
          timestamp: '2021-06-24'
        },
        {
          content: '坂バグの修正に対応。中山や阪神などは仕様ということらしい。',
          timestamp: '2021-07-09'
        },
      ]
    }
  }
}
</script>
