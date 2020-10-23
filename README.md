# blogCode【博客核心代码】
### 前提
```
  yarn global add hexo
```

### 安装
``` npm
  yarn
```
``` npm
  npm install
```

### 启动
```npm
  yarn start
```
or

```npm
  npm run start
```

### 打开个人后台文章管理
```
  http://localhost:****/admin
```

### 内容更新/发布
  方式一： 
  ```
    npm run build
  ```
  方式二： 后台发布:

  ![submit](https://user-images.githubusercontent.com/44257305/89191334-5a6c0380-d5d5-11ea-84ed-004ee36e5235.png)


### 已经完成建设
  - 404页面
  - 背景彩带
  - 看板娘插件(模型卡通男孩)
  - 评论插件(未完善)
- 

### 未完成建设

  - 站长统计
  - 网站访问量与访客量统计
  - 移动端单机事件延时的问题
  - SEO
  - 置顶小火箭

### 注意点，Lbwnb！！！
  1. 修改文章的一些属性
  ```
    // 标题
    title: JS - Es6的import、export、export default 
    // 作者
    author: Glk
    // 标签云，空的话置为 []
    tags: 
      - Es6
      - 模块化
    // 缩略图
    thumbnail: >-
      https://user-images.githubusercontent.com/44257305/96951573-5dfd8f80-151f-11eb-86cb-6be0f7a35c42.jpg
    // 分类
    categories: 空的话置为 []
      - JS
      - JS原生
    // 创建时间 
    date: 2020-10-23 10:05:00
    ---
  ```
