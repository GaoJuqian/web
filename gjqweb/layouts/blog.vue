<template>
  <div>
    <header>
      <div class="list-nav">
        <v-icon color="rgb(223, 223, 223)" @click="NavList">fa-list</v-icon>
      </div>
      <div class="logo">
        <nuxt-link to="/"><h2>GaoJuqian</h2></nuxt-link>
      </div>
      <nav>
        <ul>
          <nuxt-link to="/"><li>首页</li></nuxt-link>
          <nuxt-link to="/about"><li>关于</li></nuxt-link>
          <nuxt-link to="/"><li>读书</li></nuxt-link>
          <nuxt-link to="/"><li>归档</li></nuxt-link>
          <nuxt-link to="/"><li>仓库</li></nuxt-link>
          <nuxt-link to="/"><li>留言板</li></nuxt-link>
          <nuxt-link to="/category"><li>分类</li></nuxt-link>
        </ul>
      </nav>

      <div class="search">
        <v-text-field
          v-model="label"
          clearable
          dense
          label="搜索"
        ></v-text-field>
      </div>
    </header>
    <main>
      <div class="banner">
        <img src="@/static/img/banner.jpg" alt="" />
      </div>
      <div class="main">
        <nuxt />
      </div>
    </main>
    <footer>
      <div class="icp">{{ ICP }}</div>
      <div class="year">{{ YEAR }}</div>
    </footer>
  </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css'

export default {
  data() {
    return {
      label: '',
      ICP: '冀 ICP 备 19008505 号 - 2',
      YEAR: '© 2020 GaoJuqian'
    }
  },
  methods: {
    NavList() {
      // alert('OK')
    }
  }
}
</script>

<style>
header {
  width: 100vw;
  /* 导航栏高度 */
  height: 3.5em;
  background-color: rgba(0, 0, 0, 0.15);
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  padding: 5px 12px;
  align-items: center;
  position: fixed;
  z-index: 999;
  /* 毛玻璃效果 */
  -webkit-backdrop-filter: blur(10px);
  backdrop-filter: blur(10px);
}
nav ul {
  font-size: 16px;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: space-evenly;
}
nav ul li {
  /* 导航栏一同设置 */
  height: 3.5em;
  line-height: 3.5em;
  width: 4em;
  text-align: center;
}
nav ul li:hover {
  background-color: rgba(0, 0, 0, 0.25);
  /* color: rgb(85, 81, 255); */
  color: rgb(255, 182, 193);
}
.logo {
  height: 2em;
  /* width: 120px; */
}
.logo h2:hover {
  color: rgb(85, 81, 255);
}
nav {
  color: #dfdfdf;
  flex: 0.6;
}
.search {
  width: 120px;
  height: 2em;
}
header a {
  color: #dfdfdf;
  text-decoration: none;
}
a {
  color: black;
  text-decoration: none;
}
.router-link-active {
  text-decoration: none;
}
/* ^处理nuxt的路由标签样式 */
.banner {
  width: 100vw;
  height: 350px;
}
.banner img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* 处理图片 */
  /* 亮度 */
  -webkit-filter: brightness(0.6);
  filter: brightness(0.6);
}
.main {
  height: 100vh;
}
.list-nav {
  display: none;
}
footer {
  width: 100vw;
  height: 6em;
  background-color: #000000;
  color: #dddddd;
  text-align: left;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-evenly;
  align-items: center;
}
/* 移动端 */
@media (max-width: 768px) {
  nav {
    display: none;
  }
  .list-nav {
    display: inline;
  }
  .search {
    display: none;
  }
}
</style>
