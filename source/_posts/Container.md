---
title: Container
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

容器

<!-- more -->

## 组件 Container



## 基础使用

`Container` 属性

| 属性名     | 属性值类型    | 补充                 |
| ---------- | ------------- | -------------------- |
| width      | double        | 设置容器宽度         |
| height     | double        | 设置容器高度         |
| decoration | BoxDecoration | 设置容器（盒子）样式 |

`BoxDecoration` 属性

| 属性名 | 属性值类型 | 补充             |
| ------ | ---------- | ---------------- |
| color  | Color      | 设置容器背景颜色 |

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        color: Colors.red,
    ),
),
```

## 形状

### 矩形（默认）

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        color: Colors.red,
    ),
),
```

### 圆

`BoxDecoration` 属性

| 属性名 | 属性值类型 | 补充                                                         |
| ------ | ---------- | ------------------------------------------------------------ |
| shape  | BoxShape   | 设置容器形状<br>`BoxShape.circle` 圆形<br/>`BoxShape.rectangle` 矩形（默认值） |

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        color: Colors.red,
        shape: BoxShape.circle,
    ),
),
```

方法2： 使用圆角的方式， 实现圆; 设置容器宽高相等，圆角大小为容器一半

```dart
Container(
    width: 200,
    height: 200,
    decoration: BoxDecoration(
        color: Colors.red,
        borderRadius: BorderRadius.all(Radius.circular(100)),
    ),
),
```

### 椭圆

椭圆通过圆角实现 `Radius.elliptical(水平圆角， 垂直圆角)`， 当水平圆角为宽度的一半， 垂直圆角为高度的一半，得到椭圆

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        color: Colors.red,
        borderRadius: BorderRadius.all(Radius.elliptical(150, 100)),
    ),
),
```

## 边框

### 所有边框

`BoxDecoration` 属性

| 属性名 | 属性值类型 | 补充     |
| ------ | ---------- | -------- |
| border | Border     | 设置边框 |

`Border.all()`  设置所有边框，参数说明

| 属性名 | 属性值类型  | 补充                                                         |
| ------ | ----------- | ------------------------------------------------------------ |
| color  | Color       | 设置边框颜色                                                 |
| width  | double      | 设置边框宽度                                                 |
| style  | BorderStyle | 设置边框样式<br>`BorderStyle.solid` 实线<br/>`BorderStyle.none` 没有（去除边框） |

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        border: Border.all(
            color: Colors.red,
            width: 10,
            style: BorderStyle.solid,
        )
    ),
),
```

### 水平、垂直方向边框

`Border.symmetric(BorderSide vertical, BorderSide horizontal)` 分别设置水平（左、右）、垂直（上、下）边框

参数说明

| 属性名     | 属性值类型 | 补充                   |
| ---------- | ---------- | ---------------------- |
| vertical   | BorderSide | 设置水平（左、右）边框 |
| horizontal | BorderSide | 设置垂直（上、下）边框 |

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        border: Border.symmetric(
            vertical: BorderSide(width: 10, color: Colors.red),
            horizontal: BorderSide(width: 20, color: Colors.green),
        )
    ),
),
```

### 单独设置四个边框

`Border.fromLTRB(BorderSide top, BorderSide bottom,BorderSide left,BorderSide right,)` 分别设置四个边框

参数说明

| 属性名 | 属性值类型 | 补充       |
| ------ | ---------- | ---------- |
| left   | BorderSide | 设置左边框 |
| top    | BorderSide | 设置上边框 |
| right  | BorderSide | 设置右边框 |
| bottom | BorderSide | 设置下边框 |

```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(
        border: BoxBorder.fromLTRB(
            left: BorderSide(width: 5, color: Colors.red),
            top: BorderSide(width: 10, color: Colors.orange),
            right: BorderSide(width: 15, color: Colors.green),
            bottom: BorderSide(width: 20, color: Colors.blue),
        )
    ),
),
```

## 内边距、外边距

Container 属性

| 属性名  | 属性值类型         | 补充       |
| ------- | ------------------ | ---------- |
| padding | EdgeInsetsGeometry | 设置外边距 |
| margin  | EdgeInsetsGeometry | 设置内边距 |



```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(color: Colors.red),
    padding: EdgeInsets.all(10),
    margin: EdgeInsets.all(20),
),
```

设置所有边距

```dart
 EdgeInsets.all(10)
```

设置一个或者多个边距

```dart
EdgeInsets.only(left: 10, top: 10, right: 10, bottom: 10)
```

```dart
EdgeInsets.only(left: 10)
```

```dart
EdgeInsets.only(left: 10, top: 10,)
```

## 子元素、子元素对齐方式

Container 属性

| 属性名    | 属性值类型        | 补充                                                         |
| --------- | ----------------- | ------------------------------------------------------------ |
| child     | widget            | 组件（widget）                                               |
| alignment | AlignmentGeometry | 设置子元素对齐方式, 第一个单词代表垂直方向，第二个单词代表水平方向<br>`Alignment.topLeft`  垂直向上，水平向左<br/>`Alignment.topCenter`  垂直向上，水平居中<br/>`Alignment.topRight`  垂直向上，水平向右<br/>`Alignment.centerLeft`  垂直居中，水平向左<br/>`Alignment.center`  垂直居中，水平居中<br/>`Alignment.centerRight`  垂直居中，水平向右<br/>`Alignment.bottomLeft`  垂直向下，水平向左<br/>`Alignment.bottomCenter`  垂直向下，水平居中<br/>`Alignment.bottomRight`  垂直向下，水平向右 |



```dart
Container(
    width: 300,
    height: 200,
    decoration: BoxDecoration(color: Colors.red),
    alignment: Alignment.bottomRight,
    child: Text(
        "hello world",
        style: TextStyle(fontSize: 30),
    ),
),
```







