<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <h1>Free-GPT-UI：免费试用ChatGPT 3.5！</h1>
    <h3>在下方输入问题，点击“发送”获取答案</h3>
    <el-button
        class="scr-content"
        @click="sendMsg()"
        >发送</el-button
    >
    <Dialog ref="dialog"/>
    <h3>相关链接</h3>
    <ul>
      <li>接口调用：<a href="https://github.com/ayaka14732/ChatGPTAPIFree" target="_blank" rel="noopener">ChatGPTAPIFree</a></li>
      <li>本项目：<a href="https://github.com/Renzehua1998/Free-GPT-UI" target="_blank" rel="noopener">Free-GPT-UI</a></li>
      <li>B站主页：<a href="https://space.bilibili.com/26575098" target="_blank" rel="noopener">Renz_华</a></li>
      <li>博客：<a href="https://renzehua1998.github.io/" target="_blank" rel="noopener">Blog</a></li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
import Dialog from '@/components/dialog.vue'

export default {
  name: 'Home',
  components: {
    Dialog
  },
  methods: {
    sendMsg() {
      this.$refs.dialog.sendMsg();
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
.scr-content {
  margin-top: 20px;
  background-color: transparent !important;
  color: #fff;
}
</style>
