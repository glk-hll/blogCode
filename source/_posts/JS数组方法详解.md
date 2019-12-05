title: JS数组方法详解
author: Glk
thumbnail: >-
  https://user-images.githubusercontent.com/44257305/70061219-da913200-161e-11ea-946f-883d085ce3dd.png
date: 2019-12-03 20:54:27
tags:
---
### 这里介绍 JS 在开发过程中使用到的最频繁的几个数组原型上的方法:
_**注意事项**_：
- 以下方法后面的 Y 和 N 分别表示该方法使用否会更改原数组；
- 以下示例代码写法部分为ES6
- 以下示例代码能邪门就邪门，因为真正开发过程中的逻辑或数据不是简简单单的1、2、3、4！！！要想浏览简单的介绍及应用可以去看官方文档
___
<!-- more -->


**1. &nbsp; push(...arg)**【Y】

> **》作用:**  &emsp; 接收任意数量的参数，将它们逐个添加到数组的末尾处
**》返回值:** &emsp; 返回更改后数组的 length 值

  ``` javascript
      let arr = [1, 2]
      
      let newLength = arr.push(true, [5,6], {methodName: 'push', changeSourceArr: true  }, 'PUSH', Symbol('push'))
      
      console.log('newLength:', newLength) // 7 (type: 'number')  
  ```



**2. &nbsp; pop()**【Y】
> **》作用:**  &emsp; 移除数组末尾最后一项，减少数组的 length 值
	**》返回值:** &emsp; 返回被移除的项
``` js
	let arr = ['item1', true, {'name': 'glk'}]  
    
 let deleItem = arr.pop()
    
 console.log('arr:', arr) // ['item1', true] (type: 'array')
 
 console.log('deleItem', deleItem) // {name: "glk"} (type: 'object')
```


**3. &nbsp; shift()**【Y】
> **》作用:**  &emsp; 移除数组第一项，减少数组的 length 值
	**》返回值:** &emsp; 返回被移除的项，数组为空则返回 undefined 
``` js
	let arr = ['item1', true, {'name': 'glk'}]  
    
 let deleItem = arr.shift()
    
 console.log('arr:', arr) // [true, {'name': 'glk'}] (type: 'array')
 
 console.log('deleItem', deleItem) // 'item1' (type: 'object')
```

**4. &nbsp; unshift(...arg)**【Y】
> **》作用:**  &emsp; 接受任意数量的参数，将参数逐个添加到原数组开头处，并
	**》返回值:** &emsp; 返回更改后数组的 length 值
``` js
	let arr = ['item1', true]  
    
 let newLength = arr.unshift('newItem', false)
    
 console.log('arr:', arr) // ['newItem', false, 'item1', true](type: 'array')
 
 console.log('newLength', deleItem) // 4 (type: 'number')
```


**5. &nbsp; slice(start[, end(Number)])**【N】
> **》作用:**  &emsp; 接受两个参数，根据这两个参数从原数组中截取选定的元素
> **》返回值:** &emsp; 返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。
> **》参数:** 
	1. start: _可选。规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。_
    2. end: _可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。_
    
**以上参数解释是官方，可能在用负数的时候有点乱，这里只要记住一句话：**
&emsp;这个方法是截取数组的，截取的的方向一直都是【从左到右】，正负值只是决定了在 start 或 end 在对应值的时候是从左边还是右边开始算
``` js
	let arr = ['item1', 'item2', 'item3', 'item4']
    
 let newArr1 = arr.slice(1) // ['item2', 'item3', 'item4']
 
 let newArr2 = arr.slice(1, 3) // ['item2', 'item3']
 
 let newArr3 = arr.slice(-2) // ['item3', 'item4'] 
 
 let newArr4 = arr.slice(-2, -1) // ['item3'] 

```

**6. &nbsp; splice(start[, end(Number)])**【Y】
> **》作用:**  &emsp; 向数组中添加，或从数组删除，或替换数组中的元素，然后
> **》返回值:** &emsp; 返回被删除/替换的元素
> **》参数:** 
	1. start: _可选。规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。_
    2. end: _可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。_
    
``` js
// 1) 增加数组项
   let arr = [1, 2, 3, 4]
   
   let retVal = arr.splice(1, 0, '加入1')
   
   console.log('arr:', arr) // [1, '加入1', 2, 3, 4]
   
   console.log('retVal:', retVal) // 删除数目为 0，所以返回 []
   
   
// 2) 只删除数组项
  let arr = [1, 2, 3, 4]
   
   let retVal = arr.splice(0, 2) 
   
   console.log('arr:', arr) // [3, 4]
	
   console.log('retVal:', retVal) // [1, 2]

// 3) 删除数组项并整体替换
   let arr = [1, 2, 3, 4]
   
   let retVal = arr.splice(1, 2, 'replace')
   
   console.log('arr:', arr) // [1,'replace', 4]
	
   console.log('retVal:', retVal) // [2, 3]
   
// 4) 删除数组项并对应替换
   let arr = [1, 2, 3, 4]
   
   let retVal = arr.splice(1, 2, 'replace2', 'replace3')
   
   console.log('arr:', arr) // [1,'replace2', 'replace3', 4]
	
   console.log('retVal:', retVal) // [2, 3]
   
```

**4. &nbsp; indexOf(item[, start(Number)])**【N】
> **》作用:**  &emsp; 该方法将从头到尾地检索数组。看它是否含有对应的 item 。开始检索的位置在数组 start 处或数组的开头（没有指定 start 参数时，默认检索索引为0）。如果找到一个 item，则返回 item 的**第一次**出现的位置。
	**》返回值:** &emsp; 返回数组中 item 元素【从左往右第一次出现的位置】。没有返回 -1
``` js
	let arr = ['鸡', '翅', '包', '饭', '只', '吃', '到', '了', '饭']  
    
 arr.indexOf('饭') // 3

 arr.indexOf('饭', 3) // 3
 
 arr.indexOf('饭', 4) // 8
 
```

**4. &nbsp; lastIndexOf(item[, start(Number)])**【N】
> **》作用:**  &emsp; 该方法将从尾到头地检索数组中指定元素 item。开始检索的位置在数组的 start 处或数组的结尾（没有指定 start 参数时，默认索引为 arr.length - 1）。如果找到一个 item，则返回 item 从尾向前检索第一个次出现的项在数组中的索引。
> **》返回值:** &emsp; 返回数组中 item 元素【从右往左检索第一次出现的位置】。没有返回 -1
> **》注意:** 这里最后返回的索引值还是该项在数组中从左往右的索引值
``` js
	let arr = ['鸡', '翅', '包', '饭', '只', '吃', '到', '了', '饭']  
    
 arr.lastIndexOf('饭') // 8

 arr.lastIndexOf('饭', 3) // 3
 
 arr.lastIndexOf('饭', 4) // 3
 
 arr.lastIndexOf('饭', 2) // -1
```