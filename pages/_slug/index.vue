<template>
  <main class="main">
    <h1 class="title">{{ model_name }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://sma-tools.microcms.io/api/v1/iphone-repair/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': 'c40a31162fe14cca8714a9dd34fc021c0438' }
      }
    )
    return data
  }
}
</script>