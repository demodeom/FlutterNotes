---
title: Colors
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

Colors

<!-- more -->

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
    	color: Colors.red,
    ),
),
```

## 内置颜色

Flutter 内置了大量的颜色， 完整的颜色列表参考文档 [https://api.flutter.dev/flutter/material/Colors-class.html](https://api.flutter.dev/flutter/material/Colors-class.html)

基础颜色

```dart
Colors.red
```

```dart
Colors.orange
```

带透明度的颜色

```dart
Colors.orange[500]
```

或者

```dart
Colors.orange.shade500
```

## RGB

```
Color.fromRGBO(200, 179, 253, 1)
```

## 十六进制

比如： `#c8b3fd`，需要将`#`替换成`0xff`

```
Color(0xffc8b3fd)
```

