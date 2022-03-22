<template>
  <div class="home" style="margin-top: calc(50vh - 170px);">
    <div style="width: 50%;padding-top: 0px">
      <div style="width: 100%;display: flex;justify-content: center">
        <h1 style="color: aliceblue">{{ title }}</h1>
      </div>
      <div style="margin-bottom: 55px;">
        <a-input size="large" id="ipt" @pressEnter="Submit"/>
      </div>
      <div style="justify-content: center;display: flex">
        <a-button size="large" style="width: 30%;" @click="Submit">提交</a-button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {},
  data() {
    return{
      title: "Hello World",
    }
  },
  methods: {
    Submit() {
      window.go.main.App.GetMsg(document.getElementById("ipt").value).then(res => {
        this.title = res;
      });
    },
  },
}
</script>

<style scoped>
.home {
  width: 100%;
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
