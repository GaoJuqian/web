<template>
  <div>
    <nuxt-link to="/category">分类首页</nuxt-link>
    <div v-for="item of category" :key="item.id">
      <nuxt-link :to="'/category/' + item.id">{{ item.name }}</nuxt-link>
    </div>
    <nuxt-link to="/category/null">空</nuxt-link>
    <!-- 默认展示对应目录，index的内容 -->
    <nuxt-child />
  </div>
</template>

<script>
export default {
  data() {
    return {
      category: [
        { id: 1, name: '分类1', content: 'a' },
        { id: 2, name: '分类2', content: 'b' },
        { id: 3, name: '分类3', content: 'c' },
        { id: 4, name: '分类4', content: 'd' }
      ]
    }
  },
  layout: 'blog' // 引入自定义布局
}
</script>

<style></style>
