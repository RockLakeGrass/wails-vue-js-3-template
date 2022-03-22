<template>
  <div class="header">
    <div style="height: 25px;width: 100%;display: flex;justify-content: right" data-wails-drag>
      <div data-wails-no-drag style="display: flex">
        <div class="hover1" style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;"
             @click="miniWindowBtn">
          <LineOutlined style="color: aliceblue;font-size: 15px"/>
        </div>
        <div class="hover1" style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;"
             @click="maxWindowBtn">
          <RetweetOutlined v-if="maxStatus" style="color: aliceblue;font-size: 12px"/>
          <BorderOutlined v-else style="color: aliceblue;font-size: 12px"/>
        </div>
        <div class="hover2"
             style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;border-radius:0 6px 0 0"
             @click="closeBtn">
          <CloseOutlined style="color: aliceblue;font-size: 15px"/>
        </div>
      </div>
    </div>
    <Home/>
  </div>
</template>

<script>
import {BorderOutlined, CloseOutlined, LineOutlined,RetweetOutlined} from "@ant-design/icons-vue";
import Home from "@/components/Home.vue";

export default {
  components: {
    CloseOutlined,
    BorderOutlined,
    LineOutlined,
    RetweetOutlined,
    Home
  },
  data() {
    return{
      maxStatus: false,
    }
  },
  methods: {
    miniWindowBtn() {
      window.runtime.WindowMinimise();
    },
    maxWindowBtn() {
      if (this.maxStatus){
        window.runtime.WindowUnmaximise();
        this.maxStatus = false;
      }else{
        window.runtime.WindowMaximise();
        this.maxStatus = true;
      }
    },
    closeBtn() {
      window.runtime.Quit();
    }
  }
}
</script>
<style>
html, body, #app {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(255, 255, 255, 0);
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.header {
  height: 100%;
  width: 100%;
  background: #282b3e;
  border-radius: 6px;
  border: 0;
}

.hover1:hover {
  background: #a3a3a3;
}

.hover2:hover {
  background: #b20000;
}
</style>
