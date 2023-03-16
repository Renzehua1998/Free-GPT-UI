<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/english">English</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
    <div class="busuanzi">
      <span id="busuanzi_container_site_pv" style="">
        本站总访问量
        <span id="busuanzi_value_site_pv"></span>次
        <span class="post-meta-divider">|</span>
      </span>
      <span id="busuanzi_container_site_uv" style="">
        本站访客数
        <span id="busuanzi_value_site_uv"></span>人
      </span>
    </div>
  </div>
</template>

<script>
let script;

export default{
  mounted() {
    script = require("busuanzi.pure.js");
  },
  // 监听,当路由发生变化的时候执行
  watch: {
    $route(to, from) {
      if (to.path != from.path) {
        script.fetch();
      }
      // console.log(to.path);
    }
  },
}
</script>


<style>
body {
  background: #525467;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  text-align: center;
  color: #ffffff;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #ffffff;
}

#nav a.router-link-exact-active {
  color: #00ffff;
}

a {
  color: #00ffff;
}
</style>
