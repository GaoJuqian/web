<template>
  <div>
    <nuxt-link to="/about">关于首页</nuxt-link>
    <div v-for="item of about" :key="item.id">
      <nuxt-link :to="'/about/' + item.id">{{ item.name }}</nuxt-link>
    </div>
    <nuxt-link to="/about/null">空</nuxt-link>
    <!-- 默认展示对应目录，index的内容 -->
    <nuxt-child />
  </div>
</template>

<script>
export default {
  data() {
    return {
      about: [{ id: 1, name: '分类1', content: 'a' }]
    }
  },
  layout: 'blog' // 引入自定义布局
}
</script>

<style></style>
