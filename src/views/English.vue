<template>
  <div class="about">
    <h1>Free-GPT-UI: Using ChatGPT 3.5 for FREE!</h1>
    <h3>Typing your question below, then click "Send" button.</h3>
    <el-button
        class="scr-content"
        @click="sendMsg()"
        >Send</el-button
    >
    <Dialog ref="dialog"/>
    <h3>Related Links</h3>
    <ul>
      <li>Interface calls: <a href="https://github.com/ayaka14732/ChatGPTAPIFree" target="_blank" rel="noopener">ChatGPTAPIFree</a></li>
      <li>This project: <a href="https://github.com/Renzehua1998/Free-GPT-UI" target="_blank" rel="noopener">Free-GPT-UI</a></li>
      <li>My Bilibili: <a href="https://space.bilibili.com/26575098" target="_blank" rel="noopener">Renz_华</a></li>
      <li>My Blog: <a href="https://renzehua1998.github.io/" target="_blank" rel="noopener">Blog</a></li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
import Dialog from '@/components/dialog.vue'

export default {
  name: 'English',
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