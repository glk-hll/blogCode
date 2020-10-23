title: JS - ES6的import、export、export default
author: Glk
tags:
  - Es6
  - 模块化
thumbnail: >-
  https://user-images.githubusercontent.com/44257305/96951573-5dfd8f80-151f-11eb-86cb-6be0f7a35c42.jpg
categories:
  - JS
date: 2020-10-23 10:05:00
---

> 这里只提出一些不常用的小揪揪，module的基本语法不做介绍。感兴趣可以看看阮大神的 [ECMAScript 6 入门](https://es6.ruanyifeng.com/#docs/module)

## export
  - 批量导出
    ```javascript
      // 可以用 
      export {
        API1,
        API2
      }
      // 替代
      export API1
      ...
      ...
      export API2
    ```
  <!-- more -->
  - 设置别名
    ```javascript
      // 其他模块导入的时候只能使用 _API1，若也将 API1 导入，值为 undefined
      export {
        API1 as _API1,
      }
    ```
___


## import
  - import 语句会【执行】所加载的模块，多次重复执行同一句import语句，只会执行一次！
  - 模块的整体加载：
    ```js
      // api.js
      // 使用
      import * as API from 'modules'
      API.a
      API.b

      // 替代以下方式的导入
      import { a, b, c, d, e } from 'modules'
    ```
  - 【不允许】对导入的整体模块进行对象操作： API.a = {}  API.b = 'hhh'
  - 整体加载也同时会导入模块的默认导出，即 API 的 default 属性为 api.js 中的 export default 值
  - 若要同时导入模块中的默认导出以及其他接口可以这样：
    ```javascript
      import _, { API1, API2 } from 'modules'
    ```

___

## export与import复合使用
  - 使用场景: 某个【功能块】文件夹下的 index.js 需要【向外转发】其文件夹下某些模块的接口时！
  - 注意：API1 和 API2 实际上并没有被导入当前模块，只是相当于对外转发了这两个接口，所以当前模块不能直接使用 API1 和 API2
  ```javascript
    export { API1, API2 } from 'modules';

    // 可以简单理解为
    import { API1, API2 } from 'modules';
    export { API1, API2 };

  ```
  