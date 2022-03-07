<template>
  <div class="app">
    <h2>iPhone修理料金</h2>
    <div class="contents">
      <ul>
        <li v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/${content.id}`">
            {{ content.model_name }}
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'IndexPage',
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://sma-tools.microcms.io/api/v1/iphone-repair',
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
  h2{
    font-size:30px;
  }
</style>