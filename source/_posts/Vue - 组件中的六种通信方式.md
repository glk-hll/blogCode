title: Vue - 组件间的六种通信方式
author: Glk
thumbnail: >-
  https://user-images.githubusercontent.com/44257305/70319109-7a87cf00-185c-11ea-905c-fc7fae2f22a9.jpg
tags:
  - vue
  - 组件通信
categories:
  - Vue
date: 2019-12-06 18:57:00
---
本文借鉴自[组件通信](https://juejin.im/post/5cde0b43f265da03867e78d3)，是我看到的很好的一篇关于Vue组件间通信的文章。

关于Vue中组件的介绍可以看我的[这篇文章](),这里只做一些简单的介绍：

![组件之前的关系](https://user-images.githubusercontent.com/44257305/70318680-8fb02e00-185b-11ea-9fac-9fe8489d42f0.png)

**先看上图↑**， 上面的图是一个Vue项目很基本的部分组件之间的可能出现关系，总结如下：
- A组件有两个子组件： B组件、C组件；
- B组件和C组件之间是同级组件(兄弟组件)；
- B组件和C组件分别有自己的子组件：D组件、F组件 以及 E组件；
- D、E、F组件又同时是A组件的后代组件，反过来A组件是它们的祖先组件；   
    
那么以上关系可能就会发生下面几种对应关系之间的通信：
1. 父子组件之间的通信；
2. 兄弟组件之间的通信；
3. 祖先和后代组件之间的通信；

___

#### 上有政策下有对策，下面介绍几种能够解决上述问题的方法

- **props / $emit**
解决: 父子组件之间的通信问题

	- 1.父组件向子组件传值
   示例: parent 组件向 child 组件传递 msg 属性