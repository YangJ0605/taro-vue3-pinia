## 简介

taro-vue3-pinia 是一个使用 Taro3 + Vue3 + TypeScript + NutUi + pinia + unocss + pnpm 跨端模板，它使用了最新的前端技术栈，内置丰富的插件，有着极高的代码规范，开箱即用的跨端前端解决方案，也可用于学习参考。

## 特性

- **最新技术栈**：使用 Taro3 + Vue3 + TypeScript + NutUi + pinia + unocss + pnpm 等前端前沿技术开发
- **TypeScript**: 应用程序级 JavaScript 的语言
- **代码规范**：丰富的规范插件及极高的代码规范

## 代码仓库

- [github](https://github.com/yanbowe/taro-vue3-pinia)
- [gitee](https://gitee.com/zhongjiancrm/taro-vue3-pinia)

## Vscode 插件安装

根据项目.vscode 提示安装所需插件

## 当前实现了的功能

- Taro3 Vue3 Ts pinia
- unocss [集成](https://github.com/MellowCo/unocss-preset-weapp)
- 组件库 NutUI
- 小程序分包配置
- Taro3 配合 Vue DevTools 调试
- 样式封装 1px 问题 底部安全区域适配

## 小程序分包配置

> 随着业务代码和组件的引入越来越多，主包的大小一定会越来越大，超过 2m 的主包以后微信开发工具就无法使用预览的功能，为了提前做好准备在一开始就进行分包处理，主包只包含组件和公共代码，分包里放入业务代码

```js
// app.config.ts
export default {
  pages: ['pages/index/index'],
  window: {
    backgroundColor: '#fff',
    backgroundTextStyle: 'light',
    navigationBarBackgroundColor: '#fff',
    navigationBarTitleText: 'Taro3',
    navigationBarTextStyle: 'black'
  },
  subpackages: [
    {
      root: 'pages/packageA',
      pages: ['index/index']
    }
  ]
}
```

## 主题定制

- 使用 unocss 完善主题定制，只在 h5 有效，小程序无法对 page 动态设置 style，暂无解决方案

### 小程序配置细节

需要注意开发者工具的项目设置：

- 需要设置关闭 ES6 转 ES5 功能，开启可能报错
- 需要设置关闭上传代码时样式自动补全，开启可能报错
- 需要设置关闭代码压缩上传，开启可能报错

### 其他限制

- 小程序中不支持 `<style scoped>`，建议使用 cssModules 代替。
