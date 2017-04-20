title: 基于fis3的eslint自动检测插件

author: mewtwo

categories:
  - Node.js
  - 插件开发
  
tags:
  - fis3
  - eslint
  
date: 2017-03-09 13:45:00

---

团队发展到一定规模就需要有一个统一的标准去约束团队成员，统一编码风格。要完成这件事就需要先确定几个点：

- 用什么样的编码规范
- 是自己定义一套还是基于开源标准
- 编码规范怎么在实际开发中执行

之后在团队中开了几次头脑风暴，也实际调研了下现有的编码规范。目前比较流向的两个规范：

- feross的standard标准,目前在github上有1w多个star [github地址](https://github.com/feross/standard) [官网地址](https://standardjs.com/)
- airbnb公司的javascript标准，目前在github上star已经突破5w [github地址](https://github.com/airbnb/javascript)