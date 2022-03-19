<template>
  <div class="app">
    <TheHead/>
    <div class="main-contents">
        <div v-for="content in contents" :key="content.id" class="menu">
          <div class="link-border">
            <nuxt-link :to="`/${content.id}`">
            {{ content.model_name }}
            </nuxt-link>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import TheHead from "@/components/TheHead.vue"
export default {
  name: 'IndexPage',
  components:{
    TheHead,
  },
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://sma-tools.microcms.io/api/v1/iphone-repair?limit=50',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-MICROCMS-API-KEY': 'c40a31162fe14cca8714a9dd34fc021c0438' }
      }
    )
    return data
  }
}
</script>

<style>
.app{
  text-align:center;
}

.main-contents{
  margin-top:20px;
}

.border-line{
  border:solid;
  border-radius:10px;
}

.menu{
  display:inline-block;
  margin:10px;
}

.link-border{
  padding:5px;
  border:solid;
  border-radius:10px;
  width:200px;
  display:inline-block;
}

h2{
  font-size:30px;
}
</style>