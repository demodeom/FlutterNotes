---
title: Divider
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

分割线

<!-- more -->

| 属性名    | 属性值类型   | 补充     |
| --------- | ------------ | -------- |
| height    | double       | 高度     |
| thickness | double       | 粗细     |
| indent    | double       | 左边边距 |
| endIndent | double       | 右边边距 |
| color     | Color        | 颜色     |
| radius    | BorderRadius | 圆角     |

```dart
Text("hello world"),
Divider(height: 20,thickness: 5,indent: 20,endIndent: 50,color: Colors.red,radius: BorderRadius.circular(10),),
Text("hello world"),
```

