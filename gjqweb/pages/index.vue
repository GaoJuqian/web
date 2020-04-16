<template>
  <div>
    <VueShowdown
      :markdown="markdown"
      flavor="github"
      :options="{ emoji: true }"
    />
    <!-- markdown-edit
      <client-only>
      <mavon-editor
        v-model="article_content"
        :subfield="false"
        defaultOpen="preview"
        :toolbarsFlag="false"
        :boxShadow="false"
      />
    </client-only> -->
    <!-- <button @click="btn">点击</button>
    首页 -->
    <!-- <lunbo></lunbo> -->
  </div>
</template>

<script>
// import Lunbo from '~/components/Lunbo.vue'
export default {
  layout: 'blog', // 引入自定义布局
  components: {
    // Lunbo
  },
  data() {
    return {
      name: 'gaojuqian',
      password: '',
      img: '',
      markdown: '## markdown text'
    }
  },
  created() {
    this.$axios.get('index/article').then((res) => {
      console.log(res)
      this.markdown = res.data.test
    })
  },
  methods: {
    btn() {
      // this.$axios.get('hello').then((res) => {
      //   console.log(res)
      // })
      // const user = { username: this.name, password: this.password }
      // this.$axios.post('user', user)
    }
  }
}
</script>

<style></style>
