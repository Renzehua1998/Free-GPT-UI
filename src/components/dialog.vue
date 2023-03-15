<template>
  <div class="dialog">
    <div class="dialog-in">
        <img alt="avatar" class="avatar" src="../assets/avatar.jpeg">
        <el-input
            type="textarea"
            :rows="4"
            placeholder="Please input your question here"
            v-model="question"
            style="width: 80%; margin: 10px;">
        </el-input>
    </div>
    <div class="dialog-out">
        <img alt="openAI" class="avatar" src="../assets/openai.png">
        <el-input
            type="textarea"
            :autosize="{ minRows: 4, maxRows: 15 }"
            placeholder="Answer is here"
            v-model="answer"
            style="width: 80%; margin: 10px;">
        </el-input>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dialog',
  data() {
    return {
      question: '',
      answer: ''
    }
  },
  methods: {
    sendMsg() {
        this.$http({
            method: "post",
            url: "https://chatgpt-api.shn.hk/v1/",
            data: {
                model: "gpt-3.5-turbo",
                messages: [{"role": "user", "content": this.question}]
            },
        }).then((res) => {
            // console.log(res.data);
            this.answer = res.data.choices[0].message.content;
        })
        .catch((error) => {
            this.$message.error(error);
        });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.avatar {
    width: 10%;
    margin: 13px;
}
.dialog {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.dialog-in {
    width: 60%;
    margin: 20px;
    flex-direction: row;
    align-items: center;
    background: #303030;
}
.dialog-out {
    width: 60%;
    margin: 20px;
    flex-direction: row;
    align-items: center;
    background: #687083;
}
.dialog .el-input__inner {
  background-color: transparent !important;
  border: 1px solid #1296db;
}
</style>

