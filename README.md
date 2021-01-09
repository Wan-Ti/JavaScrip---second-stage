# JavaScrip---second-stage

## 阶段性学习

第一阶段：</br>
了解JS语法、特性、对象、数组、函数等

第二阶段：</br>
了解AJAX、设计模式、封装、面向对象、MVC

第三阶段：</br>
Vue / React

## 算法与数据结构

说实话，算法还是的自己理解了并且练习熟练了

**选择排序**

思路：</br>
使用递归实现；</br>

```
任意长度的数组排序：
let sort = (numbers) => {
  if(numbers.length >2){
     let index = minIndex(numbers)
     let min = numbers[index]
     numbers.splice(index,1)
     return [min].concat(sort(numbers))
    }else{
     return numbers[0]<numbers[1] ? numbers :numbers.reverse()
  }
} // sort([12,5,7,2])
```

使用循环实现；</br>
```
let sort = (numbers) => {
  for(let i=0;i<numbers.length-1;i++){
     let idnex = minIndex(number.slice(i)) + i
     if(index!==i){swap(numbers,index,i)}
   }
   return numbers
}

let swap = (array,i,j) => {
  let temp = array[i]
  array[i] = array[j]
  array[j] = temp
}
let minIndex = (numbers) => {
 let index = 0
 for(let i=1;i<numbers.length;i++){
   if(numbers[i] < numbers[index]){
      index = 1
    }
   }
   return index
}
```

总结：</br>
所有递归都能改成循环；

**快速排序**

```
let quickSort = arr => {
  if (arr.length <= 1） { return arr; }
  let pivotIndex = Math.floor(arr.length / 2);
  let pivot = arr.splice(pivotIndex,1)[0];
  let left = [];
  let right = [];
  for (let i = 0;i < arr.length;i++){
     if (arr[i] < pivot) { 
     left.push(arr[i])
     } else { right.push(arr[i]) }
     }
     return quickSort(left).concat([pivot],quickSort(right))
}
```

**归并排序**

```
let mergeSort = arr => {
 let k = arr.length
 if(k===1){return arr}
 let left = arr.slice(0,Math.floor(k/2))
 let right = arr.slice(Math.floor(k/2))
 return merge(mergeSort(left),mergeSort(right))
}

let merge = (a,b) => {
   if(a.length === 0) return b
   if(b.length === 0) return a
   return a[0] > b[0] ? [b[0]].concat(merge(a,b.slice(1))) : [a[0]].concat(merge(a.slice(1),b))
 }
```

**计数排序**

思路：使用哈希表作记录，发现数字N就记为N:1,如果再次发现N就加1，最后将哈希表的key打印出来，例如N：m,那么N需要打印m次

```
let countSort = arr => {
  let hashTable = {},max = 0,result = []
  for(let i = 0; i < arr.length;i++){
    if(!(arr[i] in hashTable )){
      hashTable[arr[i]] = 1
    }else{
      hashTable[arr[i] += 1
    }
    if(arr[i] > max) { max = arr[i]}
  }
  for(let j=0; j<=max;j++){
    if(j in hashTable){
      for(let i = 0;i<hashTable[j];i++){
      result.push(j)
      }
    }
  }
  return result
  }
```

计数排序的特点：</br>

数据结构不同：</br>

    · 使用了额外的hashTable;
    · 只遍历数组一遍
    · 用空间换时间
时间复杂度对比：</br>

    · 选择排序 O(n^2)
    · 快速排序 O(n log2 n)
    · 归并排序 O(n log2 n)
    · 计数排序 O(n+max)
    
  **其他排序**
  
  <a href="">冒泡排序</a> </br>
  <a href="">插入排序</a> </br>
  <a href="">希尔排序</a> </br>
  <a href="">基数排序</a> </br>
  
  ## 数据结构

关键词：

**数组**

**哈希表**

**队列Queue**

queue.push为入队/queue.shift为出队

**栈Stack**

**链表Linked List**

链表的变形有：双向链表和循环链表

**树tree**

建议阅读清华大学出版社出版的数据结构(C语言版)
