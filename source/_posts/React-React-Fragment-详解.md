title: React - React.Fragment 详解
author: Glk
thumbnail: >-
  https://user-images.githubusercontent.com/44257305/96953698-58ef0f00-1524-11eb-87ba-4efe432d8d1b.png
tags: []
categories:
  - React
date: 2020-10-23 11:31:00
---
## <>< /> 和 React.Fragment
  - <>< /> 是 React.Fragment 的语法糖，也就是说 <>< /> 基本可以当做 React.Fragment 来使用。

## 区别
  - <React.Fragment> 目前只支持传入 key 属性，未来还会增加其他属性或事件，<>< /> 则不能附带任何属性。
  - 使用场景：
    ```javascript
      return (
        <dl>
          {props.items.map(item => (
            // 没有`key`，将会触发一个key警告
            <React.Fragment key={item.id}>
              <dt>{item.term}</dt>
              <dd>{item.description}</dd>
            </React.Fragment>
          ))}
        </dl>
      )
    ```