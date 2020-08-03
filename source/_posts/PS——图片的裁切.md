title: PS——图片的裁切
author: Glk
date: 2020-06-02 10:36:28
tags:
---
经常会遇到这样一个需求：给你一张 500 * 357 的小新全家福，要求等比例缩小一下该图片的像素值，这里就取宽高的一半。
先附上原图：

![quanjiafu1](https://user-images.githubusercontent.com/44257305/89186167-00b40b00-d5ce-11ea-9757-6eb3e288a5b4.jpg)

现在需要通过PS裁切弄出下面的图片该怎么办:
![quanjiafu2](https://user-images.githubusercontent.com/44257305/89187359-c2b7e680-d5cf-11ea-9bcb-12b8cfb25c88.png)


步骤如下：
<!-- more -->

1. 在 PS 中打开大分辨率图片，然后取消对图层的锁定状态，如下：
  	![1](https://user-images.githubusercontent.com/44257305/89187839-61444780-d5d0-11ea-9742-d8996bf4501b.gif)
    
2. 点击菜单栏的图像-画布大小，设置画布大小为 250*175，注意单位是像素以及勾选掉【相对】这个选项，如下：
![2](https://user-images.githubusercontent.com/44257305/89188472-49b98e80-d5d1-11ea-8531-423810b5199d.gif)

3. 按下快捷键， ctrl + t,进入自由变换工具，然后按住周围任意触点进行轻微拖动，然后在上面选项栏直接输入 w: 250, h: 175 以最快的方式缩小至画布边缘，再 enter 或双击即可保存这次更改，最后快速导出 .png 文件也就完成了，如下：
![3](https://user-images.githubusercontent.com/44257305/89189645-dfa1e900-d5d2-11ea-8574-7d5e2566092b.gif)