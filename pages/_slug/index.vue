<template>
  <main class="main">
    <TheHead />
    <div class="border-line2">
      <div class="contents-box">
        <h1 class="model-name">{{ model_name }}</h1>
        <div class="fp-box">

          <div class="low">
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
            <div class="cont">
              <h3 class="fp-name">互換パネル</h3>
              <table class="fp-table">
                <tr>
                  <th class="fp-label1">保証なし</th>
                  <th class="fp-label2">保証あり</th>
                </tr>
                <tr>
                  <td class="fp-price">{{front1_ng}}<span>円（税抜）</span></td>
                  <td class="fp-price">{{front1_g}}<span>円（税抜）</span></td>
                </tr>
              </table>
            </div>
          </div>

          <div class="middle">
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
            <div class="cont">
              <h3 class="fp-name">高品質パネル</h3>
              <table class="fp-table">
                <tr>
                  <th class="fp-label">保証なし</th>
                  <th class="fp-label">保証あり</th>
                </tr>
                <tr>
                  <td class="fp-price">{{front2_ng}}<span>円（税抜）</span></td>
                  <td class="fp-price">{{front2_g}}<span>円（税抜）</span></td>
                </tr>
              </table>
            </div>
          </div>

          <div class="high">
            <div class="fp-img">
              <img class="img" src="../logo.png" alt="">
            </div>
            <div class="cont">
              <h3 class="fp-name">超高品質パネル</h3>
              <table class="fp-table">
                <tr>
                  <th class="fp-label">保証なし</th>
                  <th class="fp-label">保証あり</th>
                </tr>
                <tr>
                  <td class="fp-price">{{front3_ng}}<span>円（税抜）</span></td>
                  <td class="fp-price">{{front3_g}}<span>円（税抜）</span></td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </div>
      <!-- 性能などの比較表 -->
      <div class="spec-table-space">
        <table class="spec">
          <tr>
            <th></th>
            <th><h3 class="fp-type1">互換</h3></th>
            <th><h3 class="fp-type2">高品質</h3></th>
            <th><h3 class="fp-type3">超高品質</h3></th>
          </tr>
          <tr>
            <td>画質（品質）</td>
            <td>△</td>
            <td>◯</td>
            <td>◎</td>
          </tr>
          <tr>
            <td>消費電力</td>
            <td>△</td>
            <td>◯</td>
            <td>◯</td>
          </tr>
          <tr>
            <td>料金</td>
            <td>◎</td>
            <td>◯</td>
            <td>△</td>
          </tr>
        </table>
      </div>

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

.border-line2{
  width:100%;
  margin:0 auto;
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
  font-size:40px;
  border-bottom:dashed gray;
  margin-bottom:50px;
  font-weight:bold;
}

.fp-name{
  border-bottom:dotted black;
  font-weight:bold;
  font-size:120%;
}

.cont{
  background-color:white;
  margin:10px;
  border-radius:10px;
}

.low{
  background-color:#C47022;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
  width:30%;
}

.middle{
  background-color:#C9CACA;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
  width:35%;
}

.high{
  background-color:#DAB300;
  border-radius:10px;
  display:inline-block;
  margin:10px 5px;
  width:30%;
}

.fp-type1{
  background-color:#C47022;
  border-radius:10px;
  color:white;
}

.fp-type2{
  background-color:#C9CACA;
  border-radius:10px;
  color:white;
}

.fp-type3{
  background-color:#DAB300;
  border-radius:10px;
  color:white;
}

.fp-table{
  margin:0 auto;
}

.fp-label{
  text-align:center;
}

.spec{
  border-radius:10px;
  background-color:#10101010;
  margin:0 auto;
  text-align:center;
}

.spec th{
  width:20%;
}

.fp-img{
  margin:0 auto;
  width:200px;
}

.img{
  border-radius:10px;
  margin-top:10px;
}

.spec-table{
  text-align:center;
  margin:0 auto;
}

td{
  text-align:center;
  border:solid white;
}

.fp-price{
  font-size:20px;
}

.spec-table-space{
  margin-top:20px;
}

span{
  margin-left:5px;
  font-size:13px;
}
</style>