title: 基于fis3的eslint自动检测插件

author: mewtwo

categories:
  - 随笔
  
tags:
  - fis3
  - eslint
  - nodejs
  - 插件开发
  
date: 2017-03-09 13:45:00

---

## 起因

团队发展到一定规模就需要有一个统一的标准去约束成员，统一编码风格。要完成这件事就需要先确定几个事：

- 用什么样的编码规范
- 是自己定义一套还是基于开源标准
- 编码规范怎么在实际开发中执行

## 选择规范
在团队中开了几次头脑风暴，也实际调研了下现有的编码规范。目前比较流向的两个规范：

- feross 的 standard 标准,目前在 github 上有1w多个star [github地址](https://github.com/feross/standard) [官网地址](https://standardjs.com/)
- airbnb 公司的 javascript 标准，目前在 github 上 star 已经突破5w [github地址](https://github.com/airbnb/javascript)

虽然 airbnb 公司的方案已有 5w 个 star，不过 standard 标准大有赶超的意思，所以最后选择了基于standard来做 js 规范。

## 确定方案
好了，现在确定了编码规范，剩下的就是怎么去落地标准。如果只是让每个人去学习标准并不能保证所有人都能严格的执行标准去写代码，所以最好的办法还是在开发阶段就发现问题，并且必须要解决了错误才能继续开发，这样就能保证大家都是一样的标准了。

由于团队使用的是百度的 [fis3](http://fis.baidu.com/) 作为构建工具，所以第一想法就是用 fis3+eslint 来检查代码。
于是就在 fis3 的插件列表中搜了下，找到几款基于 eslint 的 fis3 插件：

![fis3 eslint](http://op292cjvq.bkt.clouddn.com/fis3/eslint/DE834AC8-D396-47AF-A8C0-EC3BDD94B83D.png 'fis3 eslint')

但是美中不足的是这些插件大都是在终端中显示错误信息，而且错误信息的格式也不优雅：
![fis3 eslint zsh](http://op292cjvq.bkt.clouddn.com/fis3/eslint/4DFC04BF-9DEE-4162-A31E-62EC731245FB.png 'fis3 eslint zsh')

基于以上原因最终确定自己开发一款基于fis3，eslint和standard标准的插件。

## 钩子
