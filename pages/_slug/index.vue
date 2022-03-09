<template>
  <main class="main">
    <TheHead />
    <div class="border-line">
      <div class="contents-box">
        <h1 class="model-name">{{ model_name }}</h1>
        <div class="fp-box">

          <div class="low">
<<<<<<< HEAD
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
=======
            <img class="fp-img" src="" alt="">
>>>>>>> parent of 193ccff (updata)
            <div class="cont">
              <h3 class="fp-name">互換パネル</h3>
              <table>
                <tr>
                  <th class="fp-label">保証なし</th>
                  <th class="fp-label">保証あり</th>
                </tr>
                <tr>
                  <td>{{front1_ng}}円（税抜）</td>
                  <td>{{front1_g}}円（税抜）</td>
                </tr>
              </table>
            </div>
          </div>

          <div class="middle">
<<<<<<< HEAD
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
=======
            <img class="fp-img" :src="front1_img" alt="">
>>>>>>> parent of 193ccff (updata)
            <div class="cont">
              <h3 class="fp-name">高品質パネル</h3>
              <table>
                <tr>
                  <th class="fp-label">保証なし</th>
                  <th class="fp-label">保証あり</th>
                </tr>
                <tr>
                  <td>{{front2_ng}}円（税抜）</td>
                  <td>{{front2_g}}円（税抜）</td>
                </tr>
              </table>
            </div>
          </div>

          <div class="high">
<<<<<<< HEAD
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
=======
            <img class="fp-img" src="" alt="">
>>>>>>> parent of 193ccff (updata)
            <div class="cont">
              <h3 class="fp-name">超高品質パネル</h3>
              <table>
                <tr>
                  <th class="fp-label">保証なし</th>
                  <th class="fp-label">保証あり</th>
                </tr>
                <tr>
                  <td>{{front3_ng}}円（税抜）</td>
                  <td>{{front3_g}}円（税抜）</td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="spec-table">
      <!-- 性能などの比較表 -->
      <table>
        <tr>
          <th></th>
          <th>互換</th>
          <th>高品質</th>
          <th>超高品質</th>
        </tr>
      </table>
    </div>
    <p class="published-at">最終更新日：{{ publishedAt }}</p>
  </main>
</template>

<script>
import axios from 'axios'
import TheHead from "@/components/TheHead.vue"
export default {
  components:{
    TheHead,
  },
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://sma-tools.microcms.io/api/v1/iphone-repair/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': 'c40a31162fe14cca8714a9dd34fc021c0438' }
      }
    )
    return data
  },
}
</script>

<style>

.border-line{
  width:80%;
  margin:0 auto;
  border:none white;
}

.published-at{
  text-align:right;
  margin-right:10px;
  font-size:10px;
}

.contents-box{
  padding:10px;
}

.fp-box{
  text-align:center;
}

.model-name{
  text-align:center;
  font-size:30px;
}

.fp-name{
  border-bottom:dotted black;
}

.cont{
  background-color:white;
  margin:10px;
  border-radius:10px;
}

.low{
  background-color:gray;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
}

.middle{
  background-color:aquamarine;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
}

.high{
  background-color:yellow;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
}

th .fp-label{
  width:50%;
}

.spec-table{
  text-align:center;
}
</style>