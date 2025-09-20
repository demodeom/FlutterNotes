---
title: Card
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
  - Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

一个Material Design卡片：一个带有轻微圆角和高度阴影的面板。

<!-- more -->



一个Material Design卡片：一个带有轻微圆角和高度阴影的面板。

| 属性名             | 属性值类型         | 补充                 |
| ------------------ | ------------------ | -------------------- |
| color              | Color              | 背景颜色             |
| shadowColor        | Color              | 眼影颜色             |
| shape              | ShapeBorder        | 形状（圆角、倒角等） |
| borderOnForeground | bool               | 边框层级             |
| margin             | EdgeInsetsGeometry | 外边距               |
| child              | Widget             | 子元素               |





```dart
Card(
            color: Colors.yellow,
            margin: EdgeInsets.all(20),
            shape: BeveledRectangleBorder(borderRadius: BorderRadius.all(Radius.elliptical(10,20))),
            child: Row(
              mainAxisAlignment: MainAxisAlignment.spaceAround,
              children: [
                Container(
                  width: 100,
                  height: 100,
                  margin: EdgeInsets.symmetric(vertical: 20),
                  decoration: BoxDecoration(
                    color: Colors.red,
                  ),
                ),
                Container(
                  width: 100,
                  height: 100,
                  decoration: BoxDecoration(
                    color: Colors.red,
                  ),
                ),
                Container(
                  width: 100,
                  height: 100,
                  decoration: BoxDecoration(
                    color: Colors.red,
                  ),
                ),
              ],
            ),
          )
```



### `ShapeBorder` 的核心概念

`ShapeBorder` 及其子类主要定义了两件事：

1. **形状 (Shape)**：例如矩形、圆形、斜角等。
2. **描边 (Stroke)**：形状周围的边框。

### 常用子类

Flutter 提供了多个 `ShapeBorder` 的子类来实现不同的形状效果：

1. **`RoundedRectangleBorder` (圆角矩形边框)**
   这是最常用的一个，专门用来创建带圆角的矩形，完美实现 Material Design 卡片的样式。
   - **主要属性：**
     - `borderRadius`: 设置圆角大小，类型为 `BorderRadius`。
       - `BorderRadius.circular(double radius)`：所有角使用相同的圆角半径。
       - `BorderRadius.only(...)`：分别指定每个角的圆角半径（例如 `topLeft`, `bottomRight`）。
       - `BorderRadius.horizontal(...)`：分别设置左、右两边的圆角。
       - `BorderRadius.vertical(...)`：分别设置上、下两边的圆角。
     - `side`: 设置边框的粗细和颜色，类型为 `BorderSide`。
2. **`CircleBorder` (圆形边框)**
   将一个形状定义为圆形。
   - **属性：**
     - `side`: 设置圆形轮廓的粗细和颜色。
3. **`BeveledRectangleBorder` (斜角矩形边框)**
   创建带有切角（斜角）的矩形，而不是圆角。
   - **属性：**
     - `borderRadius`: 设置斜角的大小。
     - `side`: 设置边框。
4. **`StadiumBorder` (体育场形状/胶囊形状边框)**
   创建两端是半圆形、中间是矩形的形状，类似于一个体育场跑道或胶囊。`Chip`  widget 默认使用此形状。
5. **`ContinuousRectangleBorder` (连续矩形边框)**
   创建具有连续平滑曲线的圆角矩形，与 `RoundedRectangleBorder` 的圆弧曲线相比，它的角更“平滑”或“流畅”，是另一种美学选择。