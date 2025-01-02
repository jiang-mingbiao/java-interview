# VUE3学习笔记

### 1、简介

作者：尤雨夕

### 2、创建VUE3工程

备注：目前vue-cli已处于维护模式，官方推荐基于Vite创建项目

2.1、基于vue-vli创建

```bash
## 查看@vue/cli版本，确保@vue/cli版本在4.5.0以上
vue --version

## 安装或者是升级你的@vue/cli
nmp install -g @vue/cli

## 执行创建命令
vue create vue_test

```

2.2、基于vite创建（推荐）

vite是新一代前端构建工具，官网地址：https://vitejs.cn ，vite的优势如下
1.轻量快速的热重载（HMR）,能实现极速的服务启动

2.对TypeScript、JSX、CSS等支持开箱即用

3.真正的按需编译，不再等待整个应用编译完成

4.webpage构建与vite构建

```bash
## 1.创建命令
npm create vue@latest

## 2.配置具体配置
## 配置项目名称
Project name: vue3_test
## 是否添加TypeScript支持
Add TypeScript? Yes
## 是否添加JSX支持
Add JSX No
## 是否添加路由环境
Add Vue Router for Single Page Application development? No
## 是否添加pinia环境
Add Pinia for state management? No
## 是否添加单元测试
Add vitest for Unit Testing? No
## 是否添加端到端测试方案
Add an End-to-End Testing Solution? No
## 是否添加ESLint语法检查
Add ESLint for code quality? Yes
## 是否添加Prettiert代码格式化
Add Prettier for code formatting? No


```

3、