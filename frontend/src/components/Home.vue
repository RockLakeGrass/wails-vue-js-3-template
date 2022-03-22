<template>
  <div class="home">
    <div style="width: 250px;padding-top: 50px">
      <div style="width: 100%;display: flex;justify-content: center">
        <h1 style="color: aliceblue">{{ title }}</h1>
      </div>
      <div style="margin-bottom: 15px;">
        <a-input id="ipt" @pressEnter="Greet"/>
      </div>
      <div style="justify-content: center;display: flex">
        <a-button @click="Submit">提交</a-button>
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
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
