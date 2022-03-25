<h3>
    Wails-Vuejs3.x-template
</h3>
<p align="center">
    <a herf="./LICENSE">
        <img alt="license" src = "https://img.shields.io/badge/license-GPL--3.0-blue"/>
    </a>
    <img alt="platform" src = "https://img.shields.io/badge/platform-windows%20%7C%20macos%20%7C%20linux-brightgreen">
</p>
<p align="center">
  基于Vue3.x的Wails模板
</p>

## 预览

![DesignSketch](./DesignSketch.png)

## 新建项目

### 先决条件
* go 和 wails
* vscode 与 插件 f5anything
* nodejs 与 npm
* vue-cli 并且包含 vue-cli-service
* git

### 创建
```
wails init -n [你的应用名称] -t https://gitee.com/rocklakegrass/wails-vue-js-3-template.git
```

### VScode 配置文件
此模板自带`VSCode`配置文件，需要`f5anything`插件的支持。
自带的位置文件为了兼容`ARM64`与`x86 32bit`弃用`dlv`，因为`dlv`不支持这些架构

如果需要自己的配置文件，可以自行配置 `.vscode/launch.json`

## 参考文档
前端部分使用了 `Vue`、`Vue-cli`和`Ant Design Vue`

* Vue: 使用 Vue 3.x 版本，具体使用方式请参考[Vue3.x 官方文档](https://v3.vuejs.org/guide/introduction.html)
* Vue-cli: 使用Vue-cli 3.x 版本，具体使用方式请参考[Vue Cli 3.x 官方文档](https://cli.vuejs.org/zh/guide/installation.html)
* Ant Design Vue: 使用antd组件库，具体使用方式请参考[Ant Design Vue 官方文档](https://www.antdv.com/docs/vue/introduce-cn/)
* [Zero的Wails Vue3模板](https://gitee.com/zero_clown/wails-vue3-template)
* 然后您就可以参考 Wails [官方文档](https://wails.top/zh-Hans/docs/introduction)开始开发您的应用啦!