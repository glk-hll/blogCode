title: Css-利用伪元素的 content 属性实现 tooltip 插件的功能
author: Glk
tags:
  - css
  - 开发小技巧
  - 伪元素
categories:
  - 前端开发/CSS
date: 2020-02-06 12:07:00
---
&nbsp;&nbsp;__当要实现元素 hover 的时候显示提示信息，如果用 title 属性觉得效果太弱，但
是又不想用JS写，更不想引入一个 tooltip 第三方的大库，这个时候可以用CSS3的
attr 属性实现，将想要展示的提示内容放到一个属性里面，而且样式可以由自己设计！__

```html
	<p>其实, <span data-title='Are you sure?'>我一直在努力！</span></p>

	<style>
     p{
        padding-top: 20px;
        color: #333;
      }

      span[data-title]{
      	position: relative;
      }
      
      span[data-title]:hover:before{
        content: attr(data-title);
        position: absolute;
        top: -160%;
        left: 50%;
        height: 20px;
        background-color: #FF9800;
        border-radius: 5px;
        padding: 5px;
        color: white;
        transform: translateX(-50%);
        white-space: nowrap;
      }

      /* 小三角形 */
      span[data-title]:hover::after{
        content: '';
        position: absolute;
        top: -35%;
        left: 50%;
        border-left: 10px solid transparent;
        border-right: 10px solid transparent;
        border-top: 10px solid #FF9800;
        transform: translateX(-50%);
      }
	</style>
```
上面最核心的代码就是 content: attr(data-title); 

由此介绍下 content 属性可以使用哪些常见的值:

- [String] 使用 '' 包括一段字符串将作为该伪元素显示的内容
- attr() 将用当前伪元素父元素的某个属性值作为该伪元素显示的内容(如图片的 alt 属性或 a链接的 href 属性等)
- url() 引用媒体文件作为该伪元素显示的内容(如 url('./public/images/avatar.png'))


关于 **小三角形** 有一篇专门介绍如何用 Css 绘制常见的小图形的，可以[看这里]()
关于 **伪元元素** 的介绍可以[看这里]()