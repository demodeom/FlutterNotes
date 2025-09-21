---
title: Button
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutter
cover: https://s21.ax1x.com/2025/09/20/pV4wFqx.png
---

Button

<!-- more -->

## TextButton

Material 风格设计的文本按钮



| 属性名     | 属性值类型    | 补充                 |
| ---------- | ------------- | -------------------- |
| width      | double        | 设置容器宽度         |
| height     | double        | 设置容器高度         |
| decoration | BoxDecoration | 设置容器（盒子）样式 |



```dart
TextButton(
    onPressed: () => {},
    style: ButtonStyle(),
    child: Text("登录"),
),
```

图标显示在左侧

```dart
TextButton.icon(onPressed: ()=>{}, label: Text("闹钟"),icon: Icon(Icons.alarm),),
```

图标显示在右侧

```dart
TextButton.icon(onPressed: ()=>{}, label: Text("闹钟"),icon: Icon(Icons.alarm),iconAlignment: IconAlignment.end,),
```



## OutlinedButton

Material 风格设计的边框文本按钮，其本质是 在`TextButton` 按钮基础上添加边框

## ElevatedButton

在文本按钮的基础上，添加边框、背景颜色、边框阴影