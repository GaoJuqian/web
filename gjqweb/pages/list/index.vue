<template>
  <div>
    <h2>分类列表</h2>
    <div v-for="item of category" :key="item.id">
      <nuxt-link :to="'/list/' + item.id">{{ item.name }}</nuxt-link>
    </div>
  </div>
</template>

<script>
// import Logo from '~/components/Logo.vue'
// import VuetifyLogo from '~/components/VuetifyLogo.vue'

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
  }
  // components: {
  //   Logo,
  //   VuetifyLogo
  // }
}
</script>

<style></style>
