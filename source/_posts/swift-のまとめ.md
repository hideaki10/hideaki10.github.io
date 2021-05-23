---
title: swift のまとめ
date: 2021-03-10 16:42:44
tags:
---


# struct


# class 

# structとclassの区別
  ## class 和 struct 在内存中的储存方式不同（储存方式不同的意思？)
  ## class 支持继承  struct不支持
  ## class 必须写construct struct有默认的不是必须


```swift
class Car {
    init(brand:String)
}

class Sedan: Car{

} 

let car = Sedan(brand:"tes")


```


# extension
扩展一个f
```swift