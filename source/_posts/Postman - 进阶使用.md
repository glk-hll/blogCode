title: Postman - 进阶使用
author: Glk
tags: []
thumbnail: >-
  https://user-images.githubusercontent.com/44257305/96853854-6c9b6680-148d-11eb-9e88-19a394ba5d27.jpg
categories: []
date: 2020-10-20 17:31:00
---
  > 注意： 以下所有带【】 的关键词都是为了更方便的在 Postman 中找到对应的操作！

### 工作环境搭建
  - 创建个人工作空间【Workspace】，习惯格式： '项目名称'，(如 '非遗CMS'）;

  - 在【Workspace】下新建 请求收藏夹【Collections】，如创建【user】收藏夹，该目录下可能有的请求项如：【用户登录】、【用户登出】【刷新token】;

  <!-- more -->
___

### 关于Collections
  - 收藏夹可以【Share】到其他工作空间【Workspace】或团队【Team】中。

  - 创建新的请求项【Request】记得要保存在请求收藏夹中【Collections】中，方便再次调用，不重要的请求不要保留，保证收藏夹的所有请求项的唯一性！

  -删除工作空间或团队下的 Collections（请求目录）千万不要【右击 -> Delete】或者 打开目录小面板下的【Delete】进行删除。删除也会连同其他使用到该目录的工作空间下的该目录。应该选择小面板中的 【Remove from workspace】来进行删除只针对当前工作目录的目录。
___

### 关于Request
  - 可以为请求项新增某些预设的 Headers （如某些接口必须带上 token ，就可以为其单独添加一个预设值，方便其他请求项使用）。

  - 请求项中的 Body 栏的属性以及属性值的填写可以直接使用 【Bulk Edit】的命令进行批量编辑，支持复制粘贴！！！

___
### 切换环境&变量
  > 一般真实项目中不同的环境使用的接口也是有细微的区别的，主要体现在接口请求跟地址上。
  1. postman 提供了一种 【Environment】的功能，我们可以在【Workspace】下新增不同的环境（如dev、pro等），
    再在不同的环境中新增不同的【VARIABLE（变量）】，该变量可以设置【INITIAL VALUE】和【CURRENT VALUE】。
    - 变量可以在任何【Request】的任何位置上使用，比如 请求地址中、Params中、Headers中、Body中...，
    - 使用方法：
      ```
        {{变量名}}
      ```
      如：
        ```
        {{base_url}}/stat/total
        ``` 
    - 这样就可以实现针对不同环境来请求不用的服务器
  2. postman 还提供另外一种【Globals】功能，用来添加一些全局变量。当然，全局变量意味着切换到任何环境都可以继续使用。
___

### 团队协作

  - 创建 Team 邀请其他成员加入进行协作；

  - 邀请对象为用户创建 postman 的邮箱，邀请之后可以为该用户设置项目权限等。

___

最终大致的感觉应该是这个样子滴：


  ![xiaoguo](https://user-images.githubusercontent.com/44257305/96851178-5344eb00-148a-11eb-83bc-ec0545b13aae.png)

