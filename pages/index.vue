<template>
  <layout-wrapper>
    <layout-visual
      title="From Drupal to NUXT"
      message="Drupalからコンテンツをゲットしてみる。"
    />
    <div class="w-full md:max-w-3xl mx-auto pt-20 px-6 md:px-0">
      <base-heading>Drupalからのデータ</base-heading>
      <div class="mb-20">
        <layout-information-list
          v-for="(item, index) in infoItems"
          :kry="index"
          :title="item.attributes.title"
          :body="item.attributes.body.value"
          :recipe="item.attributes.field_recipe.processed"
        />
      </div>
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ $config }) {
    const info = await axios.get(`${$config.apiUrl}`)
    return {
      infoItems: info.data.data,
    }
  },
}
</script>

<style>
.visual-home {
  background-image: url('~@/assets/img/visual-home.jpg');
}
</style>
