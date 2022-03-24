<template>
  <div class="header">
    <div style="height: 25px;width: 100%;display: flex;justify-content: right" data-wails-drag>
      <div v-if="platfrom != 'darwin'" data-wails-no-drag style="display: flex" :style="getPlatfrom() == 'linux' ? 'margin-left:calc(100% - 105px);' : ''">
        <div class="MinorMax" style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;"
             @click="minWindow">
          <LineOutlined style="color: aliceblue;font-size: 15px"/>
        </div>
        <div class="MinorMax" style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;"
             @click="maxWindow">
          <RetweetOutlined v-if="maxStatus" style="color: aliceblue;font-size: 12px"/>
          <BorderOutlined v-else style="color: aliceblue;font-size: 12px"/>
        </div>
        <div class="close"
             style="width: 35px;height: 25px;display: flex;justify-content: center;align-items: center;border-radius:0 6px 0 0"
             @click="closeWindow">
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
      platfrom: "windows",
    }
  },
  mounted() {
    window.go.main.App.PullPlatform().then(res => {
      this.platfrom = res;
    });
  },
  methods: {
    getPlatfrom() {
      return this.platfrom;
    },
    minWindow() {
      window.runtime.WindowMinimise();
    },
    maxWindow() {
      if (this.maxStatus){
        window.runtime.WindowUnmaximise();
        this.maxStatus = false;
      }else{
        window.runtime.WindowMaximise();
        this.maxStatus = true;
      }
    },
    closeWindow() {
      window.runtime.Quit();
    }
  }
}
</script>
<style>
html, body, #app {
  font-size: 30px;
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
  background: #064468f1;
  border-radius: 6px;
  border: 0;
}

.MinorMax:hover {
  background: #006aa8f1;
}

.close:hover {
  background: #b20000f1;
}
</style>
